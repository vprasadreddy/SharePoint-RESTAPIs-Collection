# SharePoint-RESTAPIs-Collection

### To get files in a folder
{SharePointSiteURL}/_api/web/GetFolderByServerRelativeUrl('DocumentsLibraryDisplayName/FolderName')?$expand=Folders,Files

### To get all Lists and Libraries in a Site using _vti_bin/listdata.svc
{SharePointSiteURL}/_vti_bin/listdata.svc

### To get List Items using _vti_bin/listdata.svc
{SharePointSiteURL}/_vti_bin/listdata.svc/ListDisplayNameInSentenceCaseWithoutSpaces
Note: ListDisplayNameInSentenceCaseWithoutSpaces should be in Sentence case with no spaces
Example:
ListDisplayName = "test 123"
REST URL: {SharePointSiteURL}/_vti_bin/listdata.svc/Test123

### To get User Profile Properties in SharePoint
{SharePointSiteURL}/_api/SP.UserProfiles.PeopleManager/GetPropertiesFor(accountName=@v)?@v='YourLoginAccountName'

REST API with CAML Query
Type: POST
URL: {SharePointSiteURL}/_api/web/lists/GetByTitle('ListDisplayName')/GetItems
Headers:
Content-Type : application/json;odata=verbose
Accept : application/json;odata=verbose
X-RequestDigest : $("#__REQUESTDIGEST").val()

### SharePoint Rest API Context Info to get request digest value
Type: POST
URL: {SharePointSiteURL}/_api/contextinfo

### REST API to get all items in a List
{SharePointSiteURL}/_api/web/lists/GetByTitle('ListDisplayName')/items?$select=*

### REST API to get only 1 item from the List
{SharePointSiteURL}/_api/web/lists/GetByTitle('ListDisplayName')/items(1)

### REST API to get site groups
{SharePointSiteURL}/_api/Web/sitegroups

### REST API to get users from a SharePoint group
{SharePointSiteURL}/_api/Web/SiteGroups/GetByName('Group1')/users

### REST API to get user profile properties by User Full Name
{SharePointSiteURL}/_api/web/siteusers?$filter=Title eq 'UserFullName'

### REST API to get List Entity Type Full Name
{SharePointSiteURL}/_api/web/lists/GetByTitle('ListDisplayName')/ListItemEntityTypeFullName

### REST API To Get List Item Attachments
{SharePointSiteURL}/_api/web/lists/GetByTitle('ListDisplayName')/items(1)/AttachmentFiles

### REST API to get Document properties from a Document Library
{SharePointSiteURL}/_api/web/lists/GetByTitle('ListDisplayName')/items(1)?$select=FileLeafRef,FileRef,ContentType,ContentTypeId,ContentType/Id,ContentType/Name&$expand=ContentType

### REST API with $expand to get Lookup field value
{SharePointSiteURL}/_api/web/lists/GetByTitle('ListDisplayName')/items(1)?$select=State2/Title,State2/Id&$expand=State2

### Rest API with $expand property to get SharePoint People Picker field values
{SharePointSiteURL}/_api/web/lists/GetByTitle('ListDisplayName')/items(1)?$select=*,FileRef,Reviewer/Title,Reviewer/EMail&$expand=Reviewer
