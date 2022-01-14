# sentinel_azure_mandatory_tags
A simple example for requesting mandatory tags using sentinel in TFC

## To Do
In order to use Sentinel in Terraform Cloud, you'll first need to create a policy set.

In the Organization menu at the top of the window, Go to -> **Settings**, then -> **Policy Sets**

To create a new policy set, click the "Create a new policy set" button; to edit an existing set, click its entry in the list. Click the "Create policy set" or "Update policy set" button when finished.

When creating or editing a policy set, the following fields are available:

- **Name:** The name of the policy set, which is used in the UI. Must be unique to your organization. Accepts letters, numbers, -, and _.
- **Description:** A description of the policy set's purpose. The description can be any length and supports Markdown rendering.
- **Scope of policies:** Whether the set should be enforced on all workspaces, or only on a chosen list of workspaces.
- **VCS repo or "Upload via API":** This area allows selecting a VCS repository from an existing OAuth client connection. Choosing "Upload via API" will not configure VCS integration, and instead tarballs of policy sets may be uploaded via the API. See the policy set versions for more information on uploading policy sets using the API.
- **VCS Branch:** This field allows specifying the branch within a VCS repository from which to import new versions of policies. If left blank, the value your version control provides as the default branch of the VCS repository is used.
- **Policies Path:** This field allows specifying a sub-directory within a VCS repository for the policy set files. This allows maintaining multiple policy sets within a single repository. The value of this field should be the path to the directory containing the sentinel.hcl configuration file of the policy set you wish to configure. If left blank, the root of the repository is used. A leading / may be used, but is optional (relative paths are assumed to originate from the root of the repository).
- **Workspaces:** Which workspaces the policy set should be enforced on. This is only shown when the scope of policies is set to "Policies enforced on selected workspaces." Use the drop-down menu and "Add workspace" button to add workspaces, and the trash can (🗑) button to remove them.
- **Parameters:** A list of key/value parameters that will be sent to the Sentinel runtime when a policy check is being performed for the policy set. If the value can be parsed as JSON, it will be sent to Sentinel as the corresponding type (string, boolean, integer, map or list). If it fails JSON validation, it will be sent as a string. For more information on parameters, see the Sentinel parameter documentation.

