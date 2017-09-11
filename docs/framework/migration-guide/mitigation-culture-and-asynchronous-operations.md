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
# <a name="mitigation-culture-and-asynchronous-operations"></a><span data-ttu-id="bd6cc-102">Entschärfung: Kultur und asynchrone Vorgänge</span><span class="sxs-lookup"><span data-stu-id="bd6cc-102">Mitigation: Culture and Asynchronous Operations</span></span>
<span data-ttu-id="bd6cc-103">Bei Apps für [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und höhere Versionen werden <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> im <xref:System.Threading.ExecutionContext> eines Threads gespeichert, der durch asynchrone Vorgänge verläuft.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-103">For apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and later versions, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are stored in a thread's <xref:System.Threading.ExecutionContext>, which flows across asynchronous operations.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="bd6cc-104">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="bd6cc-104">Impact</span></span>  
 <span data-ttu-id="bd6cc-105">Aufgrund dieser Änderung werden Änderungen an den Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in Aufgaben widergespiegelt, die später asynchron ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-105">As a result of this change, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are reflected in tasks which are later run asynchronously.</span></span> <span data-ttu-id="bd6cc-106">Dies weicht vom Verhalten früherer .NET Framework-Versionen ab, die <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in allen asynchronen Aufgaben auf die Systemstandardwerte zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-106">This differs from the behavior of previous .NET Framework versions, which would reset <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to the system default  in all asynchronous tasks.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="bd6cc-107">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="bd6cc-107">Mitigation</span></span>  
 <span data-ttu-id="bd6cc-108">Apps, die von dieser Änderung betroffen sind, können sie auf eine von zwei Arten umgehen:</span><span class="sxs-lookup"><span data-stu-id="bd6cc-108">Apps affected by this change can work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="bd6cc-109">Durch das explizite Festlegen der gewünschten <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>- oder <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>-Eigenschaft als erstem Vorgang in einer asynchronen Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-109">By explicitly setting the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> property as the first operation in an asynchronous task.</span></span>  
  
-   <span data-ttu-id="bd6cc-110">Durch Entscheidung für das alte Verhalten ohne dynamisch geänderte Werte der Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> durch das Hinzufügen des folgenden `AppContextSwitchOverrides`-Elements zur Konfigurationsdatei der Anwendung:</span><span class="sxs-lookup"><span data-stu-id="bd6cc-110">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by adding the following `AppContextSwitchOverrides` element to the application's configuration file:</span></span>  
  
    ```xml  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="bd6cc-111">Durch Entscheidung für das alte Verhalten ohne dynamisch geänderte Werte der Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> durch programmgesteuertes Festlegen des folgenden Kompatibilitätsschalters:</span><span class="sxs-lookup"><span data-stu-id="bd6cc-111">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by setting the following compatibility switch programatically:</span></span>  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bd6cc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd6cc-112">See Also</span></span>  
 [<span data-ttu-id="bd6cc-113">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="bd6cc-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

