# GitHub Release Tool

A tool to manage releases across mutual GitHub repos

## It Will

- Look at the tags on the main repo (in config.json) and calculate the next version using semvar (Major, Minor, Patch)
 - Collate All PRs across main and core repos (in config.json) into a changelog
- Present a List of proposed changes so that the user can double check and cancel if necessary
- If the user agrees
   - Tag the main repo and all core components with the new version using the GitHub API
   - Create/Update the Version file in the main databox repo
   - Create the release on the main repo using the GitHub API with the generated changelog

## Building
```
   go get github.com/Toshbrown/GHR

   cd [to go path]/src/github.com/Toshbrown/GHR

   go build ghrelease.go
```

## Usage
```
  -config string
    	path of the config file (default "./config.json")
  -major
    	Major release
  -minor
    	Minor release
  -patch
    	Patch/Bugfix release (default true)
```