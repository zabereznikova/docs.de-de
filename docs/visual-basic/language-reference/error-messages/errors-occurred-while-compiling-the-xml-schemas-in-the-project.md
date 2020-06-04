---
title: Fehler beim Kompilieren der XML-Schemas im Projekt
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 919c6873ba63addb776d756a58c44a3fe3f0ec3d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409626"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="9d48d-102">Fehler beim Kompilieren der XML-Schemas im Projekt</span><span class="sxs-lookup"><span data-stu-id="9d48d-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="9d48d-103">Fehler beim Kompilieren der XML-Schemas im Projekt.</span><span class="sxs-lookup"><span data-stu-id="9d48d-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="9d48d-104">Aus diesem Grund ist XML IntelliSense nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9d48d-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="9d48d-105">Fehler in einem XSD-Schema (XML Schema Definition), das im Projekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="9d48d-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="9d48d-106">Dieser Fehler tritt auf, wenn Sie eine XSD-Schema Datei (XSD-Datei) hinzufügen, die in Konflikt mit dem vorhandenen XSD-Schemaset für das Projekt steht.</span><span class="sxs-lookup"><span data-stu-id="9d48d-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="9d48d-107">**Fehler-ID:** BC36810</span><span class="sxs-lookup"><span data-stu-id="9d48d-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9d48d-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9d48d-108">To correct this error</span></span>  
  
- <span data-ttu-id="9d48d-109">Doppelklicken Sie im Fenster **Fehlerliste** auf die Warnung.</span><span class="sxs-lookup"><span data-stu-id="9d48d-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="9d48d-110">Visual Basic gelangen Sie zu dem Speicherort in der XSD-Datei, der die Quelle der Warnung ist.</span><span class="sxs-lookup"><span data-stu-id="9d48d-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="9d48d-111">Korrigieren Sie den Fehler im XSD-Schema.</span><span class="sxs-lookup"><span data-stu-id="9d48d-111">Correct the error in the XSD schema.</span></span>  
  
- <span data-ttu-id="9d48d-112">Stellen Sie sicher, dass alle erforderlichen XSD-Schema Dateien (XSD-Dateien) im Projekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9d48d-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="9d48d-113">Möglicherweise müssen Sie im Menü **Projekt** auf **alle Dateien anzeigen** klicken, um die XSD-Dateien in **Projektmappen-Explorer**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d48d-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="9d48d-114">Klicken Sie mit der rechten Maustaste auf eine XSD-Datei, und klicken Sie dann auf **in Projekt einschließen** , um die Datei in das Projekt einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="9d48d-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
- <span data-ttu-id="9d48d-115">Wenn Sie den XML-zu-Schema-Assistenten verwenden, kann dieser Fehler auftreten, wenn Sie Schemas mehr als einmal aus derselben Quelle ableiten.</span><span class="sxs-lookup"><span data-stu-id="9d48d-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="9d48d-116">In diesem Fall können Sie die vorhandenen XSD-Schema Dateien aus dem Projekt entfernen, eine neue XML-Schema Element Vorlage hinzufügen und dann den XML-Schema-Assistenten mit allen anwendbaren XML-Quellen für das Projekt bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9d48d-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
- <span data-ttu-id="9d48d-117">Wenn kein Fehler in Ihrem XSD-Schema identifiziert wird, verfügt der XML-Compiler möglicherweise nicht über genügend Informationen, um eine ausführliche Fehlermeldung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9d48d-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="9d48d-118">Möglicherweise erhalten Sie ausführlichere Fehlerinformationen, wenn Sie sicherstellen, dass die XML-Namespaces für die XSD-Dateien, die im Projekt enthalten sind, mit den XML-Namespaces identisch sind, die für das XML-Schema in Visual Studio festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="9d48d-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d48d-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d48d-119">See also</span></span>

- [<span data-ttu-id="9d48d-120">Fehlerliste Fenster</span><span class="sxs-lookup"><span data-stu-id="9d48d-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)
- [<span data-ttu-id="9d48d-121">XML</span><span class="sxs-lookup"><span data-stu-id="9d48d-121">XML</span></span>](../../programming-guide/language-features/xml/index.md)
