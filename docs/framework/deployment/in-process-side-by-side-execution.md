---
title: Prozessinterne parallele Ausführung
ms.date: 03/30/2017
helpviewer_keywords:
- in-process side-by-side execution
- side-by-side execution, in-process
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
ms.openlocfilehash: 0c699f90143a87b7e7bee24c892efe2936a9399e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716482"
---
# <a name="in-process-side-by-side-execution"></a>Prozessinterne parallele Ausführung
Ab .NET Framework 4 können Sie mit prozessinternem parallelem Hosting mehrere Versionen der Common Language Runtime (CLR) in einem einzigen Prozess ausführen. Standardmäßig werden verwaltete COM-Komponenten mit der .NET Framework-Version ausgeführt, mit der sie erstellt wurden, unabhängig von der .NET Framework-Version, die für den Prozess geladen wird.  
  
## <a name="background"></a>Hintergrund  
 .NET Framework bot schon immer paralleles Hosting für verwaltete Codeanwendungen. Vor .NET Framework 4 stand diese Funktion jedoch nicht für verwaltete COM-Komponenten zur Verfügung. In der Vergangenheit wurden verwaltete COM-Komponenten, die in einen Prozess geladen wurden, entweder mit der Version der bereits geladenen Runtime oder mit der neuesten installierten Version von .NET Framework ausgeführt. Wenn diese Version nicht mit der COM-Komponente kompatibel war, ist die Komponente fehlgeschlagen.  
  
 .NET Framework 4 bietet eine neue Herangehensweise des parallelen Hostings, wodurch Folgendes sichergestellt werden kann:  
  
- Die Installation einer neuen Version von .NET Framework hat keinen Einfluss auf vorhandene Anwendungen.  
  
- Anwendungen werden auf der Version des .NET Framework aufgeführt, mit dem sie erstellt wurden. Sie verwenden nicht die neue Version des .NET Framework, es sei denn, es wird ausdrücklich darauf hingewiesen. Es ist für Anwendungen, zu der ein Übergang stattfindet, jedoch einfacher, eine neue Version von .NET Framework zu verwenden.  
  
## <a name="effects-on-users-and-developers"></a>Auswirkungen auf Benutzer und Entwickler  
  
- **Endbenutzer und Systemadministratoren**. Diese Benutzer können nun bei der Installation einer Version der Runtime sicherer sein, wenn sie diese entweder eigenständig oder mit einer Anwendung erstellen. Dies hat keinen Einfluss auf deren Computer. Vorhandene Anwendungen werden genauso wie vorher ausgeführt.  
  
- **Anwendungsentwickler**. Das parallele Hosting hat so gut wie keine Auswirkungen auf Anwendungsentwickler. Standardmäßig werden Anwendungen immer auf der Version des .NET Framework ausgeführt, auf dem sie erstellt wurden; dies hat sich nicht verändert. Jedoch können Entwickler dieses Verhalten außer Kraft setzen und Anwendungen dazu bringen, unter einer neueren Version des .NET Framework zu laufen (siehe [Szenario 2](#scenarios)).  
  
- **Bibliotheksentwickler und Consumer**. Das parallele Hosting löst nicht die Probleme mit der Kompatibilität, denen Bibliotheksentwickler gegenüberstehen. Eine Bibliothek, die direkt durch eine Anwendung geladen wird, entweder durch einen Direktverweis oder einen <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Aufruf, verwendet weiterhin die Runtime von <xref:System.AppDomain>, in der sie geladen wurde. Sie sollten Ihre Bibliotheken für alle .NET Framework-Versionen testen, die Sie unterstützen möchten. Wenn eine Anwendung mithilfe der .NET Framework 4-Runtime kompiliert wird, aber eine Bibliothek enthält, die mit einer früheren Runtime erstellt wurde, nutzt diese Bibliothek ebenso die .NET Framework 4-Runtime. Wenn Sie jedoch über eine Anwendung verfügen, die mithilfe einer früheren Runtime erstellt wurde, sowie über eine Bibliothek, die mit .NET Framework 4 erstellt wurde, müssen Sie für Ihre Anwendung die Verwendung von .NET Framework 4 erzwingen (siehe [Szenario 3](#scenarios)).  
  
- **Entwickler verwalteter COM-Komponenten**. Früher wurden die verwalteten COM-Komponenten automatisch mithilfe der aktuellsten Version der Runtime ausgeführt, die auf dem Computer installiert war. Sie können nun COM-Komponenten für die Version der Runtime ausführen, mit der sie erstellt wurden.  
  
     So wie in der folgenden Tabelle gezeigt, können Komponenten, die mit der .NET Framework-Version 1.1 erstellt wurden, parallel mit Komponenten der Version 4 ausgeführt werden. Sie können jedoch nicht mit Komponenten der Version 2.0, 3.0 oder 3.5 ausgeführt werden, da das parallele Hosting für diese Versionen nicht verfügbar ist.  
  
    |.NET Framework-Version|1.1|2.0 - 3.5|4|  
    |----------------------------|---------|----------------|-------|  
    |1.1|Nicht zutreffend|Nein|Ja|  
    |2.0 - 3.5|Nein|Nicht zutreffend|Ja|  
    |4|Ja|Ja|Nicht zutreffend|  
  
> [!NOTE]
> .NET Framework-Versionen 3.0 und 3.5 werden inkrementell auf Version 2.0 erstellt und müssen nicht parallel ausgeführt werden. Sie sind an und für sich dieselbe Version.  
  
<a name="scenarios"></a>   
## <a name="common-side-by-side-hosting-scenarios"></a>Häufige Szenarios des parallelen Hostings  
  
- **Szenario 1:** Eine Native Anwendung, die COM-Komponenten verwendet, die mit früheren Versionen von .NET Framework erstellt wurden.  
  
     Installierte .NET Framework-Versionen: .NET Framework 4 und alle anderen Versionen von .NET Framework, die von den COM-Komponenten verwendet werden.  
  
     Vorgehensweise: In diesem Szenario unternehmen Sie nichts. Die COM-Komponenten werden mit der Version des .NET Framework ausgeführt, mit der sie registriert wurden.  
  
- **Szenario 2:** Mit .NET Framework 2.0 SP1 erstellte verwaltete Anwendung, die bevorzugt mit .NET Framework 2.0 ausgeführt werden soll, jedoch auch mit .NET Framework 4 ausgeführt werden kann, falls Version 2.0 nicht vorhanden ist.  
  
     Installierte .NET Framework-Versionen: Eine frühere Version von .NET Framework sowie .NET Framework 4.  
  
     Vorgehensweise: Verwenden Sie in der [Anwendungskonfigurationsdatei](../configure-apps/index.md) im Anwendungsverzeichnis das [Element \<startup>](../configure-apps/file-schema/startup/startup-element.md) und das [Element \<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md), die wie folgt festgelegt sind:  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
- **Szenario 3:** Native Anwendung, die COM-Komponenten verwendet, die mit früheren Versionen von .NET Framework erstellt wurden und die Sie mit .NET Framework 4 ausführen möchten.  
  
     Installierte .NET Framework-Versionen: .NET Framework 4.  
  
     Vorgehensweise: Verwenden Sie in der Anwendungskonfigurationsdatei im Anwendungsverzeichnis das `<startup>`-Element, mit dem `useLegacyV2RuntimeActivationPolicy`-Attribut, das auf `true` festgelegt ist, sowie das `<supportedRuntime>`-Element, das wie folgt festgelegt ist:  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel stellt einen nicht verwalteten COM-Host dar, der eine verwaltete COM-Komponente mithilfe der Version von .NET Framework ausführt, für deren Verwendung die Komponente kompiliert wurde.  
  
 Um das folgende Beispiel auszuführen, kompilieren und registrieren Sie die folgende verwaltete COM-Komponente mithilfe von .NET Framework 3.5. Um die Komponente zu registrieren, klicken Sie im **Projekt**-Menü auf **Eigenschaften**, auf die Registerkarte **Erstellen**, und aktivieren Sie dann das Kontrollkästchen **Für COM-Interop registrieren**.  
  
```csharp
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
  
 Kompilieren Sie die folgende nicht verwaltete C++-Anwendung, die das COM-Objekt aktiviert, das durch das vorherige Beispiel erstellt wurde.  
  
```cpp
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
  
## <a name="see-also"></a>Siehe auch

- [\<startup>-Element](../configure-apps/file-schema/startup/startup-element.md)
- [\<supportedRuntime> Element](../configure-apps/file-schema/startup/supportedruntime-element.md)
