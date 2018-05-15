---
title: Fehler beim Kompilieren der XML-Schemas im Projekt
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 0cc565809792c619ca9903f9ef9b029b51a8aa17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="24a5a-102">Fehler beim Kompilieren der XML-Schemas im Projekt</span><span class="sxs-lookup"><span data-stu-id="24a5a-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="24a5a-103">Fehler beim Kompilieren der XML-Schemas im Projekt.</span><span class="sxs-lookup"><span data-stu-id="24a5a-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="24a5a-104">Aus diesem Grund ist die XML-IntelliSense nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="24a5a-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="24a5a-105">Es ist ein Fehler in einem XML-Schemadefinition (XSD)-Schema, das im Projekt enthalten.</span><span class="sxs-lookup"><span data-stu-id="24a5a-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="24a5a-106">Dieser Fehler tritt auf, wenn Sie eine XSD-Schemadatei (.xsd) hinzufügen, die Konflikte mit vorhandenen XSD-Schema für das Projekt festgelegt.</span><span class="sxs-lookup"><span data-stu-id="24a5a-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="24a5a-107">**Fehler-ID:** BC36810</span><span class="sxs-lookup"><span data-stu-id="24a5a-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="24a5a-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="24a5a-108">To correct this error</span></span>  
  
-   <span data-ttu-id="24a5a-109">Doppelklicken Sie auf die Warnung in der **Fehlerliste** Fenster.</span><span class="sxs-lookup"><span data-stu-id="24a5a-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="24a5a-110">Visual Basic wird die Position in der XSD-Datei aufzurufen, die die Quelle der Warnung ist.</span><span class="sxs-lookup"><span data-stu-id="24a5a-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="24a5a-111">Korrigieren Sie den Fehler in der XSD-Schema.</span><span class="sxs-lookup"><span data-stu-id="24a5a-111">Correct the error in the XSD schema.</span></span>  
  
-   <span data-ttu-id="24a5a-112">Stellen Sie sicher, dass alle erforderlichen XSD-Schemadateien (.xsd) im Projekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="24a5a-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="24a5a-113">Möglicherweise müssen Sie auf klicken **alle Dateien anzeigen** auf die **Projekt** Menü, um die XSD-Dateien im **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="24a5a-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="24a5a-114">Mit der rechten Maustaste einer XSD-Datei, und klicken Sie dann auf **zu Projekt hinzufügen** auf die Datei im Projekt enthalten.</span><span class="sxs-lookup"><span data-stu-id="24a5a-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
-   <span data-ttu-id="24a5a-115">Wenn Sie die XML zu Schema-Assistenten verwenden, wird dieser Fehler kann auftreten, wenn Sie Schemas mehr als ein Mal aus der gleichen Quelle ableiten.</span><span class="sxs-lookup"><span data-stu-id="24a5a-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="24a5a-116">In diesem Fall fügen Sie Sie die vorhandenen XSD-Schema-Dateien aus dem Projekt entfernen können eine neue XML Schema-Elementvorlage, und geben Sie dann die XML zu Schema-Assistenten mit den entsprechenden XML-Datenquellen für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="24a5a-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
-   <span data-ttu-id="24a5a-117">Wenn keine Fehler in der XSD-Schema identifiziert wird, möglicherweise die XML-Compiler nicht genügend Informationen, um eine detaillierte Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="24a5a-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="24a5a-118">Möglicherweise können ausführlichere Fehlerinformationen abgerufen werden, wenn Sie sicherstellen, dass die XML-Namespaces für die XSD-Dateien in Ihrem Projekt Übereinstimmung, die XML-Namespaces für das XML-Schemaset in Visual Studio identifiziert enthalten.</span><span class="sxs-lookup"><span data-stu-id="24a5a-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a5a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24a5a-119">See Also</span></span>  
 [<span data-ttu-id="24a5a-120">Fenster „Fehlerliste“</span><span class="sxs-lookup"><span data-stu-id="24a5a-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)  
 [<span data-ttu-id="24a5a-121">XML</span><span class="sxs-lookup"><span data-stu-id="24a5a-121">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
