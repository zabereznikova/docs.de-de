---
title: Lokalisierung
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee7de15130644e63b17a6d067c5cce9088d199a0
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45591264"
---
# <a name="localization"></a><span data-ttu-id="2e76a-102">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="2e76a-102">Localization</span></span>
<span data-ttu-id="2e76a-103">Unter Lokalisierung versteht man den Vorgang, bei dem Anwendungsressourcen in lokalisierte Versionen für sämtliche von der Anwendung unterstützten Kulturen übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="2e76a-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="2e76a-104">Sie sollten erst nach Durchführung des Schritts [Überprüfung der Lokalisierbarkeit](../../../docs/standard/globalization-localization/localizability-review.md) mit dem Lokalisierungsschritt fortfahren, um sicherzustellen, dass die globalisierte Anwendung für die Lokalisierung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="2e76a-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>  
  
 <span data-ttu-id="2e76a-105">Eine zur Lokalisierung bereitstehende Anwendung wird in zwei grundlegende Blöcke unterteilt: einen Block, der alle Elemente der Benutzeroberfläche enthält, und einen Block mit ausführbarem Code.</span><span class="sxs-lookup"><span data-stu-id="2e76a-105">An application that is ready for localization is separated into two conceptual blocks, a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="2e76a-106">Der Benutzeroberflächenblock enthält nur lokalisierbare Benutzeroberflächenelemente für die neutrale Kultur, z.B. Zeichenfolgen, Fehlermeldungen, Dialogfelder, Menüs und eingebettete Objektressourcen.</span><span class="sxs-lookup"><span data-stu-id="2e76a-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="2e76a-107">Der Codeblock enthält nur den Anwendungscode, der von allen unterstützten Kulturen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2e76a-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="2e76a-108">Die Common Language Runtime unterstützt ein Satellitenassembly-Ressourcenmodell, das ausführbaren Code einer Anwendung von den jeweiligen Ressourcen trennt.</span><span class="sxs-lookup"><span data-stu-id="2e76a-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="2e76a-109">Weitere Informationen zur Implementierung dieses Modells finden Sie unter [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="2e76a-109">For more information about implementing this model, see [Resources in Desktop Apps](../../../docs/framework/resources/index.md).</span></span>  
  
 <span data-ttu-id="2e76a-110">Fügen Sie für jede lokalisierte Version Ihrer Anwendung eine neue Satellitenassembly hinzu, die den lokalisierten Benutzeroberflächenblock enthält, der in der entsprechenden Sprache für die Zielkultur übersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="2e76a-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="2e76a-111">Der Codeblock aller Kulturen sollte identisch sein.</span><span class="sxs-lookup"><span data-stu-id="2e76a-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="2e76a-112">Durch die Kombination einer lokalisierten Version des Benutzeroberflächenblocks mit dem Codeblock erzeugen Sie eine lokalisierte Version Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2e76a-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>  
  
 <span data-ttu-id="2e76a-113">Das [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] stellt den Windows Forms-Ressourcen-Editor (Winres.exe) bereit, mit dem Sie im Handumdrehen Windows Forms für Zielkulturen lokalisieren können.</span><span class="sxs-lookup"><span data-stu-id="2e76a-113">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="2e76a-114">Informationen zur Verwendung dieses Tools finden Sie unter [Winres.exe (Windows Forms-Ressourcen-Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2e76a-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e76a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e76a-115">See also</span></span>

- [<span data-ttu-id="2e76a-116">Globalisierung und Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="2e76a-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
- [<span data-ttu-id="2e76a-117">Überprüfung der Lokalisierbarkeit</span><span class="sxs-lookup"><span data-stu-id="2e76a-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
- [<span data-ttu-id="2e76a-118">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="2e76a-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
- [<span data-ttu-id="2e76a-119">Ressourcen in Desktop-Apps</span><span class="sxs-lookup"><span data-stu-id="2e76a-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
