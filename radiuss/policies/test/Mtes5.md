
**M.tes.5** All RADIUSS products must use Continuous Integration (CI) so that changes are tested as they are introduced.  Examples of CI tools include Travis CI for projects hosted on GitHub or GitLab CI for projects hosted on a GitLab instance such as LC-GitLab.  Future products may use Azure Pipelines.

> Rationale: CI helps prevent integration problems by identifying issues as they arise instead of allowing them to compound. This helps reduce rework and reduces cost and time

Examples:

RAJA with Travis CI on GitHub.  See .travis.yml 
VisIT with Circle CI on GitHub.  See  .circleci/config.yml
MFEM with AppVeyor on GitHub.  See  .appveyor.yml
Ascent with Azure Pipelines on GitHub. See azure-pipelines.yml


