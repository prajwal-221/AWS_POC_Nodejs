[Container] 2025/06/28 13:10:52.671738 Running on CodeBuild On-demand
[Container] 2025/06/28 13:10:52.671747 Waiting for agent ping
[Container] 2025/06/28 13:10:53.073799 Waiting for DOWNLOAD_SOURCE
[Container] 2025/06/28 13:10:54.297544 Phase is DOWNLOAD_SOURCE
[Container] 2025/06/28 13:10:54.298429 CODEBUILD_SRC_DIR=/codebuild/output/src2259161606/src
[Container] 2025/06/28 13:10:54.299011 YAML location is /codebuild/output/src2259161606/src/buildspec.yml
[Container] 2025/06/28 13:10:54.302647 Setting HTTP client timeout to higher timeout for S3 source
[Container] 2025/06/28 13:10:54.302806 Processing environment variables
[Container] 2025/06/28 13:10:54.730785 Selecting 'nodejs' runtime version '18' based on manual selections...
[Container] 2025/06/28 13:10:56.935076 Moving to directory /codebuild/output/src2259161606/src
[Container] 2025/06/28 13:10:56.935099 Cache is not defined in the buildspec
[Container] 2025/06/28 13:10:57.078784 Skip cache due to: no paths specified to be cached
[Container] 2025/06/28 13:10:57.079225 Registering with agent
[Container] 2025/06/28 13:10:57.204278 Phases found in YAML: 3
[Container] 2025/06/28 13:10:57.204297  INSTALL: 11 commands
[Container] 2025/06/28 13:10:57.204303  PRE_BUILD: 11 commands
[Container] 2025/06/28 13:10:57.204306  BUILD: 2 commands
[Container] 2025/06/28 13:10:57.204577 Phase complete: DOWNLOAD_SOURCE State: SUCCEEDED
[Container] 2025/06/28 13:10:57.204587 Phase context status code:  Message: 
[Container] 2025/06/28 13:10:57.381042 Entering phase INSTALL
[Container] 2025/06/28 13:10:57.508655 Running command set -e

[Container] 2025/06/28 13:10:57.516668 Running command echo 'Logging into CodeArtifact...'
Logging into CodeArtifact...

[Container] 2025/06/28 13:10:57.523912 Running command aws codeartifact login --tool npm --domain ledgerlink-domain --domain-owner 273491477087 --repository ledgerlink --region us-east-1
Successfully configured npm to use AWS CodeArtifact repository https://ledgerlink-domain-273491477087.d.codeartifact.us-east-1.amazonaws.com/npm/ledgerlink/ 
Login expires in 12 hours at 2025-06-29 01:11:08+00:00

[Container] 2025/06/28 13:11:13.156715 Running command echo 'Configuring .npmrc to use CodeArtifact with fallback to npmjs.org...'
Configuring .npmrc to use CodeArtifact with fallback to npmjs.org...

[Container] 2025/06/28 13:11:13.164283 Running command echo '@ledgerlink:registry=https://ledgerlink-domain-273491477087.d.codeartifact.us-east-1.amazonaws.com/npm/ledgerlink/' > .npmrc

[Container] 2025/06/28 13:11:13.171723 Running command echo 'registry=https://ledgerlink-domain-273491477087.d.codeartifact.us-east-1.amazonaws.com/npm/ledgerlink/' >> .npmrc

[Container] 2025/06/28 13:11:13.179125 Running command echo '//ledgerlink-domain-273491477087.d.codeartifact.us-east-1.amazonaws.com/npm/ledgerlink/:always-auth=true' >> .npmrc

[Container] 2025/06/28 13:11:13.186155 Running command echo 'Installing axios (should fallback to npmjs if not in CodeArtifact)...'
Installing axios (should fallback to npmjs if not in CodeArtifact)...

[Container] 2025/06/28 13:11:13.193573 Running command npm install axios

added 23 packages in 11s

6 packages are looking for funding
  run `npm fund` for details

[Container] 2025/06/28 13:11:24.621719 Running command echo 'Installing other dependencies...'
Installing other dependencies...

[Container] 2025/06/28 13:11:24.629613 Running command npm install

up to date in 442ms

6 packages are looking for funding
  run `npm fund` for details

[Container] 2025/06/28 13:11:25.320025 Phase complete: INSTALL State: SUCCEEDED
[Container] 2025/06/28 13:11:25.320045 Phase context status code:  Message: 
[Container] 2025/06/28 13:11:25.357412 Entering phase PRE_BUILD
[Container] 2025/06/28 13:11:25.360795 Running command set -e

[Container] 2025/06/28 13:11:25.368596 Running command if [ -n "$VERSION_TYPE" ] && [[ "$VERSION_TYPE" =~ ^(major|minor|patch)$ ]]; then FINAL_VERSION_TYPE="$VERSION_TYPE"; else FINAL_VERSION_TYPE="$DEFAULT_VERSION_TYPE"; fi

[Container] 2025/06/28 13:11:25.375808 Running command echo "Final version type: $FINAL_VERSION_TYPE"
Final version type: minor

[Container] 2025/06/28 13:11:25.382861 Running command npm version
{
  '@ledgerlink/hello-world-lib': '1.0.0',
  npm: '10.9.2',
  node: '18.20.6',
  acorn: '8.13.0',
  ada: '2.8.0',
  ares: '1.29.0',
  base64: '0.5.2',
  brotli: '1.1.0',
  cjs_module_lexer: '1.2.2',
  cldr: '44.1',
  icu: '74.2',
  llhttp: '6.1.1',
  modules: '108',
  napi: '9',
  nghttp2: '1.61.0',
  nghttp3: '0.7.0',
  ngtcp2: '1.3.0',
  openssl: '3.0.15+quic',
  simdutf: '5.6.0',
  tz: '2024a',
  undici: '5.28.5',
  unicode: '15.1',
  uv: '1.44.2',
  uvwasi: '0.0.19',
  v8: '10.2.154.26-node.37',
  zlib: '1.3.0.1-motley'
}

[Container] 2025/06/28 13:11:25.514236 Running command CURRENT_VERSION=$(npm view @ledgerlink/hello-world-lib version 2>/dev/null || echo '1.0.0')

[Container] 2025/06/28 13:11:26.196939 Running command echo "Current version: $CURRENT_VERSION"
Current version: 1.0.0

[Container] 2025/06/28 13:11:26.204457 Running command echo 'Syncing package.json to current version...'
Syncing package.json to current version...

[Container] 2025/06/28 13:11:26.211986 Running command npm version "$CURRENT_VERSION" --no-git-tag-version --allow-same-version
v1.0.0

[Container] 2025/06/28 13:11:26.451589 Running command echo "Bumping $FINAL_VERSION_TYPE version..."
Bumping minor version...

[Container] 2025/06/28 13:11:26.462163 Running command NEW_VERSION=$(npm version "$FINAL_VERSION_TYPE" --no-git-tag-version)

[Container] 2025/06/28 13:11:26.632345 Running command echo "New version: $NEW_VERSION"
New version: v1.1.0

[Container] 2025/06/28 13:11:26.641527 Phase complete: PRE_BUILD State: SUCCEEDED
[Container] 2025/06/28 13:11:26.641543 Phase context status code:  Message: 
[Container] 2025/06/28 13:11:26.679532 Entering phase BUILD
[Container] 2025/06/28 13:11:26.680592 Running command echo 'Publishing to CodeArtifact...'
Publishing to CodeArtifact...

[Container] 2025/06/28 13:11:26.688952 Running command npm publish
npm notice
npm notice 📦  @ledgerlink/hello-world-lib@1.1.0
npm notice Tarball Contents
npm notice 0B Readme.md
npm notice 1.9kB buildspec.yml
npm notice 110B index.js
npm notice 275B package.json
npm notice 103B test.js
npm notice Tarball Details
npm notice name: @ledgerlink/hello-world-lib
npm notice version: 1.1.0
npm notice filename: ledgerlink-hello-world-lib-1.1.0.tgz
npm notice package size: 1.2 kB
npm notice unpacked size: 2.4 kB
npm notice shasum: 354cc18ca366ae7ddadb37ee466fc0267e26e44e
npm notice integrity: sha512-6jLnlhB4cH/XB[...]6IwBGvdXnbeIw==
npm notice total files: 5
npm notice
npm notice Publishing to https://ledgerlink-domain-273491477087.d.codeartifact.us-east-1.amazonaws.com/npm/ledgerlink/ with tag latest and default access
+ @ledgerlink/hello-world-lib@1.1.0

[Container] 2025/06/28 13:11:27.806934 Phase complete: BUILD State: SUCCEEDED
[Container] 2025/06/28 13:11:27.806959 Phase context status code:  Message: 
[Container] 2025/06/28 13:11:27.841209 Entering phase POST_BUILD
[Container] 2025/06/28 13:11:27.844061 Phase complete: POST_BUILD State: SUCCEEDED
[Container] 2025/06/28 13:11:27.844077 Phase context status code:  Message: 
[Container] 2025/06/28 13:11:28.036142 Expanding base directory path: .
[Container] 2025/06/28 13:11:28.039646 Assembling file list
[Container] 2025/06/28 13:11:28.039659 Expanding .
[Container] 2025/06/28 13:11:28.043903 Expanding file paths for base directory .
[Container] 2025/06/28 13:11:28.043917 Assembling file list
[Container] 2025/06/28 13:11:28.043921 Expanding **/*
[Container] 2025/06/28 13:11:28.050122 Found 380 file(s)
[Container] 2025/06/28 13:11:28.143040 Set report auto-discover timeout to 5 seconds
[Container] 2025/06/28 13:11:28.143082 Expanding base directory path:  .
[Container] 2025/06/28 13:11:28.146447 Assembling file list
[Container] 2025/06/28 13:11:28.146461 Expanding .
[Container] 2025/06/28 13:11:28.149626 Expanding file paths for base directory .
[Container] 2025/06/28 13:11:28.149639 Assembling file list
[Container] 2025/06/28 13:11:28.149642 Expanding **/*
[Container] 2025/06/28 13:11:28.154371 No matching auto-discover report paths found
[Container] 2025/06/28 13:11:28.154395 Report auto-discover file discovery took 0.011355 seconds
[Container] 2025/06/28 13:11:28.154406 Phase complete: UPLOAD_ARTIFACTS State: SUCCEEDED
[Container] 2025/06/28 13:11:28.154412 Phase context status code:  Message: 
