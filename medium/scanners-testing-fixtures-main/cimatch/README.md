# Testing
There are two types of tests in this repo:

1. Most tests in this repo were created with the following concept:
    ```
    <POLICY_NAME> # coming from the cimatch `settings.yaml`.
        \--- success
                \--- (pipelines specific structure)
                    \--- main.yaml
        \--- fail(or failure)
                \--- (pipelines specific structure)
                    \--- main.yaml
    ```
where:
`success` folders -> indicate a vulnerable (or risky) fixture (== this is where we detect a vulnerability)

`failure` folders -> indicate a non-vulnerable (or risky) fixture

2. The other type of tests (v2) is structured as follows:
    ```
    <PIPELINE_TYPE> # ie azure_pipelines
        \--- <CASE_NAME> # to be used in tests
                \--- <artifact.yaml>
    ```

We should consolidate those at a later time and modify the tests