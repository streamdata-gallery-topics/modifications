---
swagger: "2.0"
x-collection-name: Atlassian
x-complete: 0
info:
  title: Jira Cloud API Move version
  description: Modifies the version's sequence within the project, which affects the
    display order of the versions in Jira. **[Permissions](https://confluence.atlassian.com/x/FQiiLQ)
    required:** _Administer Jira_ [global permission](https://confluence.atlassian.com/x/x4dKLg)
    or _Administer Projects_ [project permission](https://confluence.atlassian.com/x/yodKLg).
  termsOfService: http://atlassian.com/terms/
  version: 1.0.0
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /api/2/component/{id}:
    put:
      summary: Update component
      description: |-
        Modifies a component. Any fields included in the request are overwritten. If `leadUserName` is an empty string ("") the component lead is removed. [Permissions](https://confluence.atlassian.com/x/FQiiLQ) required: Any of the following:

        *   _Administer Jira_ [global permission](https://confluence.atlassian.com/x/x4dKLg).
        *   _Administer projects_ [project permission](https://confluence.atlassian.com/x/yodKLg).
      operationId: com.atlassian.jira.rest.v2.issue.ComponentResource.updateComponent_put
      x-api-path-slug: api2componentid-put
      parameters:
      - in: header
        name: force-account-id
      - in: path
        name: id
      responses:
        200:
          description: OK
      tags:
      - Component
  /api/2/version/{id}:
    put:
      summary: Update version
      description: Modifies a project version. **[Permissions](https://confluence.atlassian.com/x/FQiiLQ)
        required:** _Administer Jira_ [global permission](https://confluence.atlassian.com/x/x4dKLg)
        or _Administer Projects_ [project permission](https://confluence.atlassian.com/x/yodKLg).
      operationId: com.atlassian.jira.rest.v2.issue.VersionResource.updateVersion_put
      x-api-path-slug: api2versionid-put
      parameters:
      - in: path
        name: id
        description: The ID of the version
      responses:
        200:
          description: OK
      tags:
      - Version
  /api/2/version/{id}/move:
    post:
      summary: Move version
      description: Modifies the version's sequence within the project, which affects
        the display order of the versions in Jira. **[Permissions](https://confluence.atlassian.com/x/FQiiLQ)
        required:** _Administer Jira_ [global permission](https://confluence.atlassian.com/x/x4dKLg)
        or _Administer Projects_ [project permission](https://confluence.atlassian.com/x/yodKLg).
      operationId: com.atlassian.jira.rest.v2.issue.VersionResource.moveVersion_post
      x-api-path-slug: api2versionidmove-post
      parameters:
      - in: path
        name: id
        description: The ID of the version to be moved
      responses:
        200:
          description: OK
      tags:
      - Move
      - Version
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---