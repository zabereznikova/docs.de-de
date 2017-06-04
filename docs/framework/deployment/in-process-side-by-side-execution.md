---
title: "Prozessinterne parallele Ausf&#252;hrung | Microsoft Docs"
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
  - "Prozessinterne parallele Ausführung"
  - "Parallele Ausführung, Prozessintern"
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
caps.latest.revision: 25
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 25
---
# Prozessinterne parallele Ausf&#252;hrung
Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] können Sie mit prozessinternem parallelem Hosting mehrere Versionen der Common Language Runtime \(CLR\) in einem einzelnen Prozess ausführen.  Standardmäßig werden verwaltete COM\-Komponenten mit der .NET Framework\-Version verwaltet, mit der sie erstellt wurden, unabhängig von der .NET Framework\-Version, die für den Prozess geladen wird.  
  
## Hintergrund  
 .NET Framework bietet seit jeher paralleles Hosting für verwaltete Codeanwendungen, doch vor der Version [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] stand diese Funktion nicht für verwaltete COM\-Komponenten zur Verfügung.  Früher wurden verwaltete COM\-Komponenten, die in einem Prozess geladen wurden, entweder mit der Version der Laufzeit, die bereits geladen war, oder mit der am aktuellsten installierten Version von .NET Framework ausgeführt.  Wenn diese Version nicht kompatibel mit der COM\-Komponente wäre, würde die Komponente fehlschlagen.  
  
 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] bietet einen neuen Ansatz für paralleles Hosting, durch den Folgendes sichergestellt wird:  
  
-   Die Installation einer neuen Version von .NET Framework hat keine Auswirkungen auf vorhandene Anwendungen.  
  
-   Anwendungen werden für die Version von .NET Framework ausgeführt, mit der sie erstellt wurden.  Es wird nicht die neue Version von .NET Framework verwendet, sofern keine ausdrückliche Anweisung dazu vorliegt.  Es ist jedoch einfacher, wenn für Anwendungen eine neue Version von .NET Framework verwendet wird.  
  
## Auswirkungen auf Benutzer und Entwickler  
  
-   **Endbenutzer und Systemadministratoren**.  Diese Benutzer können nun mit größerer Wahrscheinlichkeit annehmen, dass bei der Installation einer neuen Version der Laufzeit – entweder unabhängig oder mit einer Anwendung – keine Auswirkungen auf die Computer auftreten.  Vorhandene Anwendungen werden wie bisher ausgeführt.  
  
-   **Anwendungsentwickler**.  Paralleles Hosting hat fast keine Auswirkungen auf Anwendungsentwickler.  Standardmäßig werden Anwendungen immer für die Version von .NET Framework ausgeführt, mit der sie erstellt wurden; dies hat sich nicht geändert.  Allerdings können Entwickler dieses Verhalten außer Kraft setzen und die Anwendung unter einer neueren Version von .NET Framework ausführen \(siehe [Szenario 2](#scenarios)\).  
  
-   **Bibliotheksentwickler und Consumer**.  Paralleles Hosting löst nicht die Kompatibilitätsprobleme von Bibliotheksentwicklern.  Eine Bibliothek, die direkt von einer Anwendung geladen wird – entweder durch einen direkten Verweis oder durch einen <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Aufruf – verwendet weiterhin die Laufzeit des <xref:System.AppDomain>\-Objekts, in das sie geladen wird.  Testen Sie die Bibliotheken für alle Versionen von .NET Framework testen, die Sie unterstützen möchten.  Wenn eine Anwendung mit der [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]\-Laufzeit kompiliert wird, aber eine Bibliothek einschließt, die mit einer früheren Laufzeit erstellt wurde, verwendet diese Bibliothek auch die [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]\-Laufzeit.  Wenn Sie jedoch über eine Anwendung verfügen, die mit einer früheren Laufzeit und einer Bibliothek erstellt wurde, die mit [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] erstellt wurde, muss die Verwendung von [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] durch die Anwendung erzwungen werden \(siehe [Szenario 3](#scenarios)\).  
  
-   **Entwickler von verwalteten COM\-Komponenten**.  Früher wurden verwaltete COM\-Komponenten automatisch mit der neuesten Version der auf dem Computer installierten Laufzeit ausgeführt.  Sie können nun COM\-Komponenten für die Version der Laufzeit ausführen, mit der sie erstellt wurden.  
  
     Entsprechend den Angaben in der folgenden Tabelle können Komponenten, die mit .NET Framework, Version 1.1, erstellt wurden, parallel mit Komponenten der Version 4 ausgeführt werden, doch sie können nicht mit Komponenten der Version 2.0, 3.0 oder 3.5 ausgeführt werden, da paralleles Hosting für diese Versionen nicht verfügbar ist.  
  
    |.NET Framework\-Version|1.1|2.0 \- 3.5|4|  
    |-----------------------------|---------|----------------|-------|  
    |1.1|Nicht zutreffend|nein|ja|  
    |2.0 \- 3.5|nein|Nicht zutreffend|ja|  
    |4|ja|ja|Nicht zutreffend|  
  
> [!NOTE]
>  Die Versionen 3.0 und 3.5 von .NET Framework werden inkrementell auf Version 2.0 erstellt. Eine parallele Ausführung ist nicht erforderlich.  Grundsätzlich handelt es sich dabei um die gleiche Version.  
  
<a name="scenarios"></a>   
## Allgemeine parallele Hostingszenarien  
  
-   **Szenario 1:** Systemeigene Anwendung, die mit früheren Versionen von .NET Framework erstellte COM\-Komponenten verwendet.  
  
     Installierte .NET Framework\-Versionen: [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] und alle anderen Versionen von .NET Framework, die von COM\-Komponenten verwendet werden.  
  
     Vorgehensweise: In diesem Szenario sind keine Schritte erforderlich.  Die COM\-Komponenten werden mit der Version von .NET Framework ausgeführt, mit der sie registriert wurden.  
  
-   **Szenario 2**: Verwaltete Anwendung, die mit [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] erstellt wurde, das Sie mit [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)] ausführen möchten, wobei Sie jedoch auch [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] für die Ausführung verwenden würden, wenn Version 2.0 nicht vorhanden ist.  
  
     Installierte .NET Framework\-Versionen: Eine frühere Version von .NET Framework und [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
     Vorgehensweise: In [Anwendungskonfigurationsdatei](../../../docs/framework/configure-apps/index.md) im Anwendungsverzeichnis, verwenden Sie [\<Starten\>\-Element](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) und [\<supportedRuntime\>\-Element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md), die festgelegt werden, wie folgt:  
  
    ```  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
-   **Szenario 3:** Systemeigene Anwendung, die mit früheren Versionen von .NET Framework erstellte COM\-Komponenten verwendet, die Sie mit [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] ausführen möchten.  
  
     Installierte .NET Framework\-Versionen: [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
     Vorgehensweise: Verwenden Sie in der Anwendungskonfigurationsdatei im Anwendungsverzeichnis das `<startup>`\-Element, wobei das `useLegacyV2RuntimeActivationPolicy`\-Attribut auf `true` und das `<supportedRuntime>`\-Element folgendermaßen festgelegt ist:  
  
    ```  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## Beispiel  
 Im folgenden Beispiel wird ein nicht verwalteter COM\-Host gezeigt, auf dem eine verwaltete COM\-Komponente ausgeführt wird. Dabei wird die Version von .NET Framework verwendet, für deren Verwendung die Komponente kompiliert wurde.  
  
 Zum Ausführen des folgenden Beispiels, kompilieren und registrieren Sie die folgende verwaltete COM\-Komponente mit [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)].  Um die Komponente, auf dem Menü **Projekt** zu registrieren, klicken auf **Eigenschaften**, auf die Registerkarte **Erstellen** und aktivieren Sie dann das Kontrollkästchen **Für COM\-Interop registrieren**.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Runtime.InteropServices;  
  
namespace BasicComObject  
{  
    [ComVisible(true), Guid("9C99C4B5-CA54-4c58-8988-49B6811BA53B")]  
    public class MyObject : SimpleObjectModel.IPrintInfo  
    {  
        public MyObject()  
        {  
        }  
        public void PrintInfo()  
        {  
            Console.WriteLine("MyObject was activated in {0} runtime in:\n\tAppDomain {1}:{2}", System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion(), AppDomain.CurrentDomain.Id, AppDomain.CurrentDomain.FriendlyName);  
        }  
    }  
}  
```  
  
 Kompilieren Sie die folgende nicht verwaltete C\+\+\-Anwendung, von der das COM\-Objekt aktiviert wird, das im vorherigen Beispiel erstellt wurde.  
  
```  
#include "stdafx.h"  
#include <string>  
#include <iostream>  
#include <objbase.h>  
#include <string.h>  
#include <process.h>  
  
using namespace std;  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    char input;  
    CoInitialize(NULL) ;  
    CLSID clsid;  
    HRESULT hr;  
    HRESULT clsidhr = CLSIDFromString(L"{9C99C4B5-CA54-4c58-8988-49B6811BA53B}",&clsid);  
    hr = -1;  
    if (FAILED(clsidhr))  
    {  
        printf("Failed to construct CLSID from String\n");  
    }  
    UUID id = __uuidof(IUnknown);  
    IUnknown * pUnk = NULL;  
    hr = ::CoCreateInstance(clsid,NULL,CLSCTX_INPROC_SERVER,id,(void **) &pUnk);  
    if (FAILED(hr))  
    {  
        printf("Failed CoCreateInstance\n");  
    }else  
    {  
        pUnk->AddRef();  
        printf("Succeeded\n");  
    }  
  
    DISPID dispid;  
    IDispatch* pPrintInfo;  
    pUnk->QueryInterface(IID_IDispatch, (void**)&pPrintInfo);  
    OLECHAR FAR* szMethod[1];  
    szMethod[0]=OLESTR("PrintInfo");   
    hr = pPrintInfo->GetIDsOfNames(IID_NULL,szMethod, 1, LOCALE_SYSTEM_DEFAULT, &dispid);  
    DISPPARAMS dispparams;  
    dispparams.cNamedArgs = 0;  
    dispparams.cArgs = 0;  
    VARIANTARG* pvarg = NULL;  
    EXCEPINFO * pexcepinfo = NULL;  
    WORD wFlags = DISPATCH_METHOD ;  
;  
    LPVARIANT pvRet = NULL;  
    UINT * pnArgErr = NULL;  
    hr = pPrintInfo->Invoke(dispid,IID_NULL, LOCALE_USER_DEFAULT, wFlags,  
        &dispparams, pvRet, pexcepinfo, pnArgErr);  
    printf("Press Enter to exit");  
    scanf_s("%c",&input);  
    CoUninitialize();  
    return 0;  
}  
  
```  
  
## Siehe auch  
 [\<startup\>\-Element](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)   
 [\<supportedRuntime\>\-Element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)