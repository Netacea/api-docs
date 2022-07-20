# Change Log
All notable changes to this project will be documented in this file.
 
The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).
 
## [0.1.0-beta] - 2022-07-20
  
### Added
 
### Changed
  
- `/domain/` to `/domains/` This change has been made to ensure all of our endpoints follow a generic plural pattern
- Attack `label` to `type` On the `domains/{domainID}/attacks` and `/domains/{domainID}/attacks/{attackID}` endpoints the attack label was previously returned which should have been mapped to a type. The type is now returned instead of the label

### Fixed
