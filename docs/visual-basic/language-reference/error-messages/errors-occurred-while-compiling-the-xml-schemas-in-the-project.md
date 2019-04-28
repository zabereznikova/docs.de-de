---
title: Fehler beim Kompilieren der XML-Schemas im Projekt
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 337fc1fb4dfc83c9b4814d3e45eb0cbe0758f7ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803279"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="3d8bd-102">Fehler beim Kompilieren der XML-Schemas im Projekt</span><span class="sxs-lookup"><span data-stu-id="3d8bd-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="3d8bd-103">Fehler beim Kompilieren der XML-Schemas im Projekt.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="3d8bd-104">Aus diesem Grund ist die XML-IntelliSense nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="3d8bd-105">Es ist ein Fehler in einem XML-Schema Definition (XSD)-Schema, das im Projekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="3d8bd-106">Dieser Fehler tritt auf, wenn Sie eine XSD-Schemadatei (.xsd) hinzufügen, die Konflikte mit vorhandenen XSD-Schema für das Projekt festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="3d8bd-107">**Fehler-ID:** BC36810</span><span class="sxs-lookup"><span data-stu-id="3d8bd-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3d8bd-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="3d8bd-108">To correct this error</span></span>  
  
- <span data-ttu-id="3d8bd-109">Doppelklicken Sie auf die Warnung in der **Fehlerliste** Fenster.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="3d8bd-110">Visual Basic gelangen Sie zu der Position in der XSD-Datei, die die Quelle der Warnung ist.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="3d8bd-111">Korrigieren Sie den Fehler in der XSD-Schema.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-111">Correct the error in the XSD schema.</span></span>  
  
- <span data-ttu-id="3d8bd-112">Stellen Sie sicher, dass alle erforderlichen XSD-Schemadateien (.xsd) im Projekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="3d8bd-113">Möglicherweise müssen Sie auf klicken **alle Dateien anzeigen** auf die **Projekt** Menü, um die XSD-Dateien im **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="3d8bd-114">Mit der rechten Maustaste einer XSD-Datei, und klicken Sie dann auf **zu Projekt** auf die Datei in Ihr Projekt einbinden.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
- <span data-ttu-id="3d8bd-115">Wenn Sie das XML to Schema-Assistenten verwenden, wird dieser Fehler kann auftreten, wenn Sie Schemas mehrmals aus derselben Quelle ableiten.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="3d8bd-116">In diesem Fall fügen Sie eine neue XML Schema-Elementvorlage, die vorhandenen XSD-Schema-Dateien aus dem Projekt entfernen können, und geben Sie dann die XML-Schema-Assistenten mit den entsprechenden XML-Datenquellen für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
- <span data-ttu-id="3d8bd-117">Wenn kein Fehler im XSD-Schema identifiziert wird, möglicherweise der XML-Compiler nicht genügend Informationen, um eine detaillierte Fehlermeldung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="3d8bd-118">Möglicherweise können Sie detailliertere Fehlerinformationen erhalten, wenn Sie sicherstellen, dass die XML-Namespaces für die XSD-Dateien in Ihrem Projekt Übereinstimmung, die XML-Namespaces, die für das XML-Schemaset in Visual Studio identifiziert enthalten.</span><span class="sxs-lookup"><span data-stu-id="3d8bd-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d8bd-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d8bd-119">See also</span></span>

- [<span data-ttu-id="3d8bd-120">Fenster „Fehlerliste“</span><span class="sxs-lookup"><span data-stu-id="3d8bd-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)
- [<span data-ttu-id="3d8bd-121">XML</span><span class="sxs-lookup"><span data-stu-id="3d8bd-121">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
