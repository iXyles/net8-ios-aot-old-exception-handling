# Repro case for iOS issue with AOT

When running this sample it'll not load on latest iOS with net8.0 (GA first release)

1. Terminal in the project & run `dotnet publish -c Release`
2. Build the docker `docker build -f ./LocalDockerfile .` (or deploy the published files to other way source to run the AOT build)
3. If docker built, just run it & expose port 80 and try open it on iPhone
4. Does not start
# Fix to make it work

Change "WasmEnableExceptionHandling" back to true, then it starts as expected, however then it'll not work correctly on older versions of Chrome (example some version of v109 which is the latest for win7)