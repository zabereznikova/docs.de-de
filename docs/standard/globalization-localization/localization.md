---
title: Lokalisierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4aaf2da77a1fab55cbebd6bfa05a2b1c74e5cbbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="localization"></a><span data-ttu-id="b296d-102">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="b296d-102">Localization</span></span>
<span data-ttu-id="b296d-103">Lokalisierung ist der Prozess der Übersetzung der Ressourcen einer Anwendung in lokalisierten Versionen für jede Kultur, die die Anwendung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b296d-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="b296d-104">Sie sollten mit dem Lokalisierung Schritt fortfahren, erst nach dem Ausführen der [Lokalisierbarkeit](../../../docs/standard/globalization-localization/localizability-review.md) Schritt, um sicherzustellen, dass die globalisierte Anwendung für die Lokalisierung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="b296d-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>  
  
 <span data-ttu-id="b296d-105">Anwendung für die Lokalisierung bereit ist, wird in zwei grundlegende Blöcke, ein Block, der alle Elemente der Benutzeroberfläche enthält und einen Block mit ausführbarem Code getrennt.</span><span class="sxs-lookup"><span data-stu-id="b296d-105">An application that is ready for localization is separated into two conceptual blocks, a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="b296d-106">Der Benutzer-Schnittstelle-Block enthält nur lokalisierbare Benutzeroberflächenelemente wie z. B. Zeichenfolgen, Fehlermeldungen, Dialogfelder, Menüs, eingebettete Objektressourcen, und so weiter für die neutrale Kultur.</span><span class="sxs-lookup"><span data-stu-id="b296d-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="b296d-107">Der Codeblock enthält nur den Anwendungscode, die von allen unterstützten Kulturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b296d-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="b296d-108">Die common Language Runtime unterstützt eine Satellitenassembly-Ressourcenmodell, das ausführbaren Code einer Anwendung von den Ressourcen trennt.</span><span class="sxs-lookup"><span data-stu-id="b296d-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="b296d-109">Weitere Informationen zum Implementieren dieses Modells finden Sie unter [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="b296d-109">For more information about implementing this model, see [Resources in Desktop Apps](../../../docs/framework/resources/index.md).</span></span>  
  
 <span data-ttu-id="b296d-110">Fügen Sie für jede lokalisierte Version der Anwendung eine neue Satellitenassembly, die den lokalisierten Schnittstelle-Block in der entsprechenden Sprache für die Zielkultur übersetzt enthält.</span><span class="sxs-lookup"><span data-stu-id="b296d-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="b296d-111">Der Codeblock für alle Kulturen sollten identisch sein.</span><span class="sxs-lookup"><span data-stu-id="b296d-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="b296d-112">Die Kombination einer lokalisierten Version des Blocks Schnittstelle Benutzer mit der Codeblock erzeugt eine lokalisierte Version der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b296d-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>  
  
 <span data-ttu-id="b296d-113">Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] stellt das Windows Forms Resource Editor (Winres.exe), die Sie zum Lokalisieren von Windows Forms für Ziel Kulturen schnell ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b296d-113">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="b296d-114">Informationen zur Verwendung dieses Tools finden Sie unter [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b296d-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b296d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b296d-115">See Also</span></span>  
 [<span data-ttu-id="b296d-116">Globalisierung und Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="b296d-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="b296d-117">Überprüfung der Lokalisierbarkeit</span><span class="sxs-lookup"><span data-stu-id="b296d-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 [<span data-ttu-id="b296d-118">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="b296d-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 [<span data-ttu-id="b296d-119">Ressourcen in Desktop-Apps</span><span class="sxs-lookup"><span data-stu-id="b296d-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
