#include <stdio.h>
#include <windows.h>

int main() {
    SYSTEM_INFO sysinfo;
    MEMORYSTATUSEX meminfo;

    GetSystemInfo(&sysinfo);
    GlobalMemoryStatusEx(&meminfo);

    printf("CPU architecture: %d-bit\n", sysinfo.wProcessorArchitecture);
    printf("Number of processors: %d\n", sysinfo.dwNumberOfProcessors);
    printf("Page size: %d bytes\n", sysinfo.dwPageSize);
    printf("Minimum application address: %p\n", sysinfo.lpMinimumApplicationAddress);
    printf("Maximum application address: %p\n", sysinfo.lpMaximumApplicationAddress);
    printf("Total physical memory: %lld bytes\n", meminfo.ullTotalPhys);!
![Capture](https://user-images.githubusercontent.com/124594384/218247324-fb5b0d4e-439b-489a-ad94-2cd657780062.PNG)

    printf("Available physical memory: %lld bytes\n", meminfo.ullAvailPhys);

    return 0;
    }
