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
    printf("Total physical memory: %lld bytes\n", meminfo.ullTotalPhys);
    printf("Available physical memory: %lld bytes\n", meminfo.ullAvailPhys);

    return 0;
}
