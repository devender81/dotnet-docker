ARG REPO=mcr.microsoft.com/dotnet/core/runtime
FROM $REPO:5.0-focal

# Install ASP.NET Core
RUN aspnetcore_version=5.0.0-alpha.1.20071.6 \
    && curl -SL --output aspnetcore.tar.gz https://dotnetcli.azureedge.net/dotnet/aspnetcore/Runtime/$aspnetcore_version/aspnetcore-runtime-$aspnetcore_version-linux-x64.tar.gz \
    && aspnetcore_sha512='9fbac9a4b8a62877316bb757052af4ac9c8c7b7fedac35a2383903a78a4e5ff61ecf665e955879078c9d854058daacfd44b7d3e6779a807f5c1607efa0138081' \
    && echo "$aspnetcore_sha512  aspnetcore.tar.gz" | sha512sum -c - \
    && tar -ozxf aspnetcore.tar.gz -C /usr/share/dotnet ./shared/Microsoft.AspNetCore.App \
    && rm aspnetcore.tar.gz