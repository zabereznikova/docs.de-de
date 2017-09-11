---
title: Fehler beim Kompilieren der XML-Schemas im Projekt | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36810
- vbc36810
dev_langs:
- VB
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7e6a835f84f2e37f4f583bc16c24cf9bb28cc92a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="fa0f8-102">Fehler beim Kompilieren der XML-Schemas im Projekt</span><span class="sxs-lookup"><span data-stu-id="fa0f8-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="fa0f8-103">Fehler beim Kompilieren der XML-Schemas im Projekt.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="fa0f8-104">Aus diesem Grund ist IntelliSense für XML nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="fa0f8-105">Es ist ein Fehler in einem XML-Schema Definition (XSD)-Schema, das im Projekt enthalten.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="fa0f8-106">Dieser Fehler tritt auf, wenn Sie eine XSD-Schemadatei (.xsd) hinzufügen, die Konflikte mit vorhandenen XSD-Schema für das Projekt festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="fa0f8-107">**Fehler-ID:** BC36810</span><span class="sxs-lookup"><span data-stu-id="fa0f8-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fa0f8-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fa0f8-108">To correct this error</span></span>  
  
-   <span data-ttu-id="fa0f8-109">Doppelklicken Sie auf die Warnung in der **Fehlerliste** Fenster.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="fa0f8-110">Visual Basic gelangen Sie zu der Position in der XSD-Datei, die die Quelle der Warnung ist.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="fa0f8-111">Korrigieren Sie den Fehler im XSD-Schema.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-111">Correct the error in the XSD schema.</span></span>  
  
-   <span data-ttu-id="fa0f8-112">Stellen Sie sicher, dass alle erforderlichen XSD-Schemadateien (.xsd) im Projekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="fa0f8-113">Möglicherweise wird auf **alle Dateien anzeigen** auf der **Projekt** Menü, um die XSD-Dateien im **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="fa0f8-114">Mit der rechten Maustaste einer XSD-Datei, und klicken Sie dann auf **zu Projekt** auf die Datei im Projekt enthalten.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
-   <span data-ttu-id="fa0f8-115">Wenn Sie das XML to Schema-Assistenten verwenden, wird dieser Fehler kann auftreten, wenn Sie Schemas mehr als einmal aus der gleichen Quelle ableiten.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="fa0f8-116">In diesem Fall fügen Sie eine neue XML zu Schema-Elementvorlage vorhandenen XSD-Schemadateien aus dem Projekt entfernen können hinzu, und stellen Sie dann die XML-Schema-Assistenten mit den entsprechenden XML-Datenquellen für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
-   <span data-ttu-id="fa0f8-117">Wenn kein Fehler im XSD-Schema angegeben wird, kann der XML-Compiler nicht genügend Informationen, um eine detaillierte Fehlermeldung haben.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="fa0f8-118">Sie können möglicherweise weitere Informationen zu erhalten, wenn Sie sicherstellen, dass die XML-Namespaces für die XSD-Dateien in Ihrem Projekt Übereinstimmung, die XML-Namespaces für das XML-Schemaset in Visual Studio identifiziert enthalten.</span><span class="sxs-lookup"><span data-stu-id="fa0f8-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0f8-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa0f8-119">See Also</span></span>  
 <span data-ttu-id="fa0f8-120">[Fehlerliste (Fenster)](https://docs.microsoft.com/visualstudio/ide/reference/error-list-window) </span><span class="sxs-lookup"><span data-stu-id="fa0f8-120">[Error List Window](https://docs.microsoft.com/visualstudio/ide/reference/error-list-window) </span></span>  
<span data-ttu-id="fa0f8-121"> [IntelliSense für XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md) </span><span class="sxs-lookup"><span data-stu-id="fa0f8-121"> [XML IntelliSense in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md) </span></span>  
<span data-ttu-id="fa0f8-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)</span><span class="sxs-lookup"><span data-stu-id="fa0f8-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)</span></span>
