# Semantic Release Tryout

## Installation
```shell
npm i -D semantic-release @semantic-release/{git,commit-analyzer,release-notes-generator,npm,changelog}
```

## Create .releaserc file
```json
{
  "branches": ["master",{ "name": "develop", "prerelease": true }],
  "plugins": [
    "@semantic-release/commit-analyzer",
    "@semantic-release/release-notes-generator",
    "@semantic-release/changelog",
  [
    "@semantic-release/npm",
    {
      "npmPublish": false
    }
  ],
  ["@semantic-release/git", {
    "assets": ["dist/", "package.json","CHANGELOG.md"],
    "message": "chore(release): ${nextRelease.version} [skip ci]\n\n${nextRelease.notes}"
  }],
  "@semantic-release/github"
  ],
  "repositoryUrl": "https://github.com/ashimjk/semantic-release-tryout"
}
```

## Run
```shell
npx semantic-release --dry-run --no-ci
```