---
title: "Entschärfung: Kultur und asynchrone Vorgänge | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2cdb578-9923-47df-9ffd-5865333ac1a4
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c2dbf60cacf47be3c448b5683b771840ef85ddaf
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-culture-and-asynchronous-operations"></a>Entschärfung: Kultur und asynchrone Vorgänge
Für Apps, die auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und höhere Versionen ausgerichtet sind, werden <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> im <xref:System.Threading.ExecutionContext> eines Threads gespeichert, der asynchrone Vorgänge durchquert.  
  
## <a name="impact"></a>Auswirkungen  
 Als Folge dieser Änderung werden Änderungen an den Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in Aufgaben widergespiegelt, die später asynchron ausgeführt werden. Dies weicht vom Verhalten in früheren .NET Framework-Versionen ab, die <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in allen asynchronen Aufgaben auf die Systemstandardwerte zurücksetzten.  
  
## <a name="mitigation"></a>Problemumgehung  
 Apps, die von dieser Änderung betroffen sind, können sie auf eine von zwei Arten umgehen:  
  
-   Durch explizites Festlegen der gewünschten <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>- oder <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>-Eigenschaft als erstem Vorgang in einer asynchronen Aufgabe.  
  
-   Durch Entscheidung für das alte Verhalten ohne dynamisch geänderte Werte der Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> durch Hinzufügen des folgenden `AppContextSwitchOverrides`-Elements zur Konfigurationsdatei der Anwendung:  
  
    ```xml  
  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
  
    ```  
  
-   Durch Entscheidung für das alte Verhalten ohne dynamisch geänderte Werte der Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> durch programmgesteuertes Festlegen des folgenden Kompatibilitätsschalters:  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
