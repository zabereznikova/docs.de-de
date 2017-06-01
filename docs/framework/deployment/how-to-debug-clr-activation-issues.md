---
title: "Gewusst wie: Debuggen von CLR-Aktivierungsproblemen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "CLR-Aktivierung, Debugprobleme"
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Debuggen von CLR-Aktivierungsproblemen
Wenn beim Ausführen der Anwendung mit der richtigen Version der Common Language Runtime \(CLR\) Probleme auftreten, können Sie CLR\-Aktivierungsprotokolle anzeigen und debuggen.  Diese Protokolle können sehr hilfreich sein, um die Ursache eines Aktivierungsproblems zu bestimmen, wenn die Anwendung eine andere als die erwartete CLR\-Version lädt oder die CLR überhaupt nicht lädt.  [.NET Framework\-Initialisierungsfehler: Verwalten der Benutzerfreundlichkeit](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md) erläutert die Erfahrung, wenn kein CLR für eine Anwendung gefunden wird.  
  
 Die CLR\-Aktivierungsprotokollierung kann mit einem HKEY\_LOCAL\_MACHINE\-Registrierungsschlüssel oder einer Systemumgebungsvariablen systemweit aktiviert werden.  Das Protokoll wird so lange generiert, bis der Registrierungseintrag bzw. die Umgebungsvariable entfernt wird.  Sie können alternativ auch mit einer Benutzervariablen oder einer für den Prozess lokalen Umgebungsvariablen einen anderen Umfang und eine andere Dauer für die Protokollierung aktivieren.  
  
 CLR\-Aktivierungsprotokolle dürfen nicht mit [Assemblybindungsprotokollen](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md) verwechselt werden. Bei diesen handelt es sich um einen vollständig anderen Protokolltyp.  
  
## So aktivieren Sie die CLR\-Aktivierungsprotokollierung  
  
#### Mithilfe der Registrierung  
  
1.  Navigieren Sie im Registrierungs\-Editor zum Ordner HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework \(auf einem 32\-Bit\-Computer\) oder HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework \(auf einem 64\-Bit\-Computer\).  
  
2.  Fügen Sie den Zeichenfolgenwert `CLRLoadLogDir` hinzu, und legen Sie für ihn einen Wert eines vollständigen Pfades zu einem vorhandenen Verzeichnis fest, in dem Sie CLR\-Aktivierungsprotokolle speichern möchten.  
  
 Die Aktivierungsprotokollierung bleibt aktiviert, bis Sie den Wert der Zeichenfolge entfernen.  
  
#### Mit einer Umgebungsvariablen  
  
-   Legen Sie die `COMPLUS_CLRLoadLogDir`\-Umgebungsvariable auf eine Zeichenfolge fest, die den vollständigen Pfad zu einem vorhandenen Verzeichnis darstellt, in dem Sie CLR\-Aktivierungsprotokolle speichern möchten.  
  
     Durch das Festlegen der Umgebungsvariablen bestimmen Sie ihren Bereich:  
  
    -   Wenn Sie sie auf Systemebene festlegen, wird die Aktivierungsprotokollierung für alle .NET Framework\-Anwendungen auf diesem Computer aktiviert, bis die Umgebungsvariable entfernt wird.  
  
    -   Wenn Sie die Umgebungsvariable auf Benutzerebene festlegen, wird die Aktivierungsprotokollierung nur für das aktuelle Benutzerkonto aktiviert.  Die Protokollierung wird fortgesetzt, bis die Umgebungsvariable entfernt wird.  
  
    -   Wenn Sie sie aus dem Prozess festlegen, bevor die CLR geladen wird, ist die Aktivierungsprotokollierung aktiviert, bis der Prozess beendet wird.  
  
    -   Wenn Sie sie mit einer Eingabeaufforderung festlegen, bevor Sie eine Anwendung ausführen, ist die Aktivierungsprotokollierung für jede Anwendung aktiviert, die von dieser Eingabeaufforderung ausgeführt wird.  
  
     Um beispielsweise Aktivierungsprotokolle im Verzeichnis c:\\clrloadlogs mit Prozessebenenumfang zu speichern, öffnen Sie ein Eingabeaufforderungsfenster und geben Sie Folgendes ein, bevor Sie die Anwendung ausführen:  
  
    ```  
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs  
    ```  
  
## Beispiel  
 CLR\-Aktivierungsprotokolle bieten eine große Menge an Daten zur CLR\-Aktivierung und zur Verwendung der CLR\-Hosting\-APIs.  Die meisten dieser Daten werden intern von Microsoft verwendet. Wie in diesem Artikel beschrieben, können einige der Daten jedoch auch für Entwickler hilfreich sein.  
  
 Das Protokoll gibt die Reihenfolge wieder, in der die CLR\-Hosting\-APIs aufgerufen wurden.  Es enthält außerdem hilfreiche Daten zu dem Satz der installierten Laufzeiten, die auf dem Computer erkannt wurden.  Das Format des CLR\-Aktivierungsprotokolls ist kein dokumentiertes Format, es kann jedoch von Entwicklern zum Beheben von CLR\-Aktivierungsproblemen genutzt werden.  
  
> [!NOTE]
>  Sie können ein Aktivierungsprotokoll erst öffnen, wenn der Prozess, der die CLR verwendet, beendet wurde.  
  
> [!NOTE]
>  CLR\-Aktivierungsprotokolle werden nicht lokalisiert, sondern immer in Englisch generiert.  
  
 Im folgenden Beispiel für ein Aktivierungsprotokoll werden die nützlichsten Informationen hervorgehoben und nach dem Protokoll beschrieben.  
  
```  
532,205950.367,CLR Loading log for C:\Tests\myapp.exe   
532,205950.367,Log started at 4:26:12 PM on 10/6/2011   
532,205950.367,-----------------------------------   
532,205950.382,FunctionCall: _CorExeMain   
532,205950.382,FunctionCall: ClrCreateInstance, Clsid: {2EBCD49A-1B47-4A61-B13A-4A03701E594B}, Iid: {E2190695-77B2-492E-8E14-C4B3A7FDD593}   
532,205950.382,MethodCall: ICLRMetaHostPolicy::GetRequestedRuntime. Version: (null), Metahost Policy Flags: 0x168, Binary: (null), Iid: {BD39D1D2-BA2F-486A-89B0-B4B0CB466891}   
532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0   
532,205950.382,Input values for ComputeVersionString follow this line   
532,205950.382,-----------------------------------   
532,205950.382,Default Application Name: C:\Tests\myapp.exe   
532,205950.382,IsLegacyBind is: 0   
532,205950.382,IsCapped is 0   
532,205950.382,SkuCheckFlags are 0   
532,205950.382,ShouldEmulateExeLaunch is 0   
532,205950.382,LegacyBindRequired is 0   
532,205950.382,-----------------------------------   
532,205950.382,Parsing config file: C:\Tests\myapp.exe   
532,205950.382,UseLegacyV2RuntimeActivationPolicy is set to 0   
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe   
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe   
532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727   
532,205950.382,ERROR: Version v2.0.50727 is not present on the machine.   
532,205950.398,SEM_FAILCRITICALERRORS is set to 0   
532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3   
532,205950.398,FunctionCall: RealDllMain. Reason: 0   
532,205950.398,FunctionCall: OnShimDllMainCalled. Reason: 0  
  
```  
  
-   **CLR Loading log** stellt den Pfad zur ausführbaren Datei bereit, die den Prozess gestartet hat, mit dem der verwaltete Code geladen wurde.  Beachten Sie, dass es sich dabei um einen systemeigenen Host handeln kann.  
  
    ```  
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe  
  
    ```  
  
-   **Installed Runtime** ist der Satz der auf dem Computer installierten CLR\-Versionen, für die eine Aktivierungsanforderung erfolgen kann.  
  
    ```  
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0  
  
    ```  
  
-   **built with version** gibt die Version der CLR an, mit der die für eine Methode, z. B. [ICLRMetaHostPolicy::GetRequestedRuntime](../Topic/ICLRMetaHostPolicy::GetRequestedRuntime%20Method.md), bereitgestellte Binärdatei erstellt wurde.  
  
    ```  
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727  
  
    ```  
  
-   **feature\-on\-demand installation** bezieht sich auf das Aktivieren von .NET Framework 3.5 unter Windows 8.  Weitere Informationen zu diesem Szenario finden Sie unter [.NET Framework\-Initialisierungsfehler: Verwalten der Benutzerfreundlichkeit](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md).  
  
    ```  
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3  
  
    ```  
  
## Siehe auch  
 [Bereitstellung](../../../docs/framework/deployment/net-framework-and-applications.md)   
 [Gewusst wie: Konfigurieren einer Anwendung für die Unterstützung von .NET Framework 4 oder 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)