# Simple .Net Core OpenTelemetry Implementation

## Usage

Very simple project to serve as my own person POC. Simply implements the Open Telemetry packages and exports the traces to the console.

## Key Changes

- Add Nuget Packages
   - OpenTelemetry.Exporter.Console
   - OpenTelemetry.Extensions.Hosting
   - OpenTelemetry.Instrumentaion.AspNetCore
- Update ConfigureServices func in Startup.cs
```
services.AddOpenTelemetryTracing(
    (builder) => builder
        .AddAspNetCoreInstrumentation()
        .AddConsoleExporter(o => o.Targets = OpenTelemetry.Exporter.ConsoleExporterOutputTargets.Console)                
    );          
```

   

## Issues

I'm not able to export traces to the DEBUG console but am able to export them to the default Console.
