---
title: "Entschärfung: Kultur und asynchrone Vorgänge"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: debcae8281c832d2815e1b9896fbbcb725c8ffc3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-asynchronous-operations"></a>Entschärfung: Kultur und asynchrone Vorgänge
Bei Apps für [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und höhere Versionen werden <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> im <xref:System.Threading.ExecutionContext> eines Threads gespeichert, der durch asynchrone Vorgänge verläuft.  
  
## <a name="impact"></a>Auswirkungen  
 Aufgrund dieser Änderung werden Änderungen an den Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in Aufgaben widergespiegelt, die später asynchron ausgeführt werden. Dies weicht vom Verhalten früherer .NET Framework-Versionen ab, die <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in allen asynchronen Aufgaben auf die Systemstandardwerte zurücksetzen.  
  
## <a name="mitigation"></a>Problemumgehung  
 Apps, die von dieser Änderung betroffen sind, können sie auf eine von zwei Arten umgehen:  
  
-   Durch das explizite Festlegen der gewünschten <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>- oder <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>-Eigenschaft als erstem Vorgang in einer asynchronen Aufgabe.  
  
-   Durch Entscheidung für das alte Verhalten ohne dynamisch geänderte Werte der Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> durch das Hinzufügen des folgenden `AppContextSwitchOverrides`-Elements zur Konfigurationsdatei der Anwendung:  
  
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

