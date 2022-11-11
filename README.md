# PostgreSQL ASP.NET Core 3.1
Project to test .NET prometheus metrics 
## Installation

Install below packages

Install-Package prometheus-net.AspNetCore
Install-Package prometheus-net
Install-Package prometheus-net.NetFramework.AspNet


Add endpoints.MapMetrics()  in the delegate body.


public void Configure(IApplicationBuilder app, ...)
{
    // ...

    app.UseEndpoints(endpoints =>
    {
        // ...

        endpoints.MapMetrics();
    });
}



Then after app.UseRouting() add app.UseHttpMetrics().


public void Configure(IApplicationBuilder app, ...)
{
    // ...

    app.UseRouting();
    app.UseHttpMetrics();

    // ...
}

