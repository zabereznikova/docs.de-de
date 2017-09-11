---
title: "Entschärfung: Kultur und Verteilervorgänge in WPF-Apps"
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
ms.assetid: 455c1452-8ce0-45ae-a092-21fb8edf1cac
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41fc52679884d547809f1c1e9f47e29eb668cb8e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a><span data-ttu-id="5c4c9-102">Entschärfung: Kultur und Verteilervorgänge in WPF-Apps</span><span class="sxs-lookup"><span data-stu-id="5c4c9-102">Mitigation: Culture and Dispatcher Operations in WPF Apps</span></span>
<span data-ttu-id="5c4c9-103">In Apps für .NET Framework 4.6 und 4.6.1 gehen Änderungen an den <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>- oder <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>-Eigenschaften, die innerhalb eines <xref:System.Windows.Threading.Dispatcher>-Objekts vorgenommen werden, am Ende dieses Dispatchervorgangs verloren.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-103">In apps that target the .NET Framework 4.6 and the .NET Framework 4.6.1, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties that are made within a <xref:System.Windows.Threading.Dispatcher> are lost at the end of that dispatcher operation.</span></span> <span data-ttu-id="5c4c9-104">Auf ähnliche Weise werden außerhalb des Dispatchervorgangs vorgenommene Änderungen an <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> möglicherweise nicht widergespiegelt, wenn der Vorgang ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-104">Similarly, changes to <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> made outside of a dispatcher operation may not be reflected when that operation executes.</span></span>  
  
 <span data-ttu-id="5c4c9-105">Der Grund liegt in einer Änderung in <xref:System.Threading.ExecutionContext>, durch die <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> im Ausführungskontext gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-105">This is due to a change in <xref:System.Threading.ExecutionContext> that causes the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to be stored in the execution context.</span></span> <span data-ttu-id="5c4c9-106">WPF-Verteilungsvorgänge speichern den Ausführungskontext, der dazu verwendet wurde, um den Vorgang zu beginnen und stellen den vorherigen Kontext wieder her, wenn der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-106">WPF dispatcher operations store the execution context used to begin the operation and restore the previous context when the operation is completed.</span></span> <span data-ttu-id="5c4c9-107">Da <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> jetzt Bestandteil dieses Kontexts sind, bleiben innerhalb eines Dispatchervorgangs an ihnen vorgenommene Änderungen außerhalb des Vorgangs nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-107">Because <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are now part of that context, changes to them within a dispatcher operation are not persisted outside of the operation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="5c4c9-108">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="5c4c9-108">Impact</span></span>  
 <span data-ttu-id="5c4c9-109">Praktisch gesehen bedeutet dies, dass Änderungen an den Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> zwischen Rückrufen der WPF-Benutzeroberfläche und anderem Code in einer WPF-Anwendung nicht weitergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-109">Practically, this means that changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties may not flow between WPF UI callbacks and other code in a WPF application.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="5c4c9-110">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="5c4c9-110">Mitigation</span></span>  
 <span data-ttu-id="5c4c9-111">Apps, die von dieser Änderung betroffen sind, können sie auf eine von zwei Arten umgehen:</span><span class="sxs-lookup"><span data-stu-id="5c4c9-111">Apps affected by this change may work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="5c4c9-112">Durch das Speichern der gewünschten <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> oder <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in einem Feld und das Überprüfen in allen <xref:System.Windows.Threading.Dispatcher>-Vorgangstexten (einschließlich Ereignisrückrufhandlern der Benutzeroberfläche), ob das richtige <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>- oder <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>-Objekt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-112">By storing the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in a field and checking in all <xref:System.Windows.Threading.Dispatcher> operation bodies (including UI event callback handlers) that the correct <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> is set.</span></span>  
  
-   <span data-ttu-id="5c4c9-113">Da sich die Änderung an <xref:System.Threading.ExecutionContext> nur auf WPF-Apps mit den Zielplattformen .NET Framework 4.6 oder .NET Framework 4.6.1 auswirkt, kann diese Änderung durch Festlegen von .NET Framework 4.5.2 oder einer Version von .NET Framework, die mit 4.6.2 beginnt, als Zielplattform vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-113">Because the change to <xref:System.Threading.ExecutionContext> only affects WPF apps that target the .NET Framework 4.6 or the .NET Framework 4.6.1, this change can be avoided by targeting the .NET Framework 4.5.2 or by targeting a version of the .NET Framework starting with 4.6.2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c4c9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c4c9-114">See Also</span></span>  
 [<span data-ttu-id="5c4c9-115">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="5c4c9-115">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

