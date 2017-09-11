---
title: "In Dateiname angegebene Datei ist keine gültige XML-Datei | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8b46b9d896f0dce401992e8a20e040b85091ba5d
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="567c2-102">Die in „Dateiname“ angegebene Datei ist keine gültige XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="567c2-102">File specified in FileName is not a valid XML file</span></span>
<span data-ttu-id="567c2-103">Der von Ihnen angegebene Dateiname gehört nicht zu einer gültigen XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="567c2-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="567c2-104">Sie können eine Dokumenttypdefinition (DTD), ein Microsoft XDR-Schemaformat (XML-Data Reduced) oder ein XSD-Schema (Sprache der XML-Schemadefinition) verwenden, um die zulässige Struktur und die Inhalte eines XML-Dokuments anzugeben.</span><span class="sxs-lookup"><span data-stu-id="567c2-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="567c2-105">XSD-Schemas sind die bevorzugte Methode zum Angeben von XML-Grammatiken in der [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="567c2-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="567c2-106">In einigen früheren Versionen von Visual Studio stellt der **XML-Designer** den Designer für typisierte DataSets und XML-Schemas dar.</span><span class="sxs-lookup"><span data-stu-id="567c2-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="567c2-107">Der **XML-Designer** kann weiterhin zum Erstellen und Bearbeiten von XML-Schemadateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="567c2-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="567c2-108">In [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], der Designer zum Erstellen und Bearbeiten typisierter Datasets ist die **Dataset-Designer**.</span><span class="sxs-lookup"><span data-stu-id="567c2-108">However, in [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="567c2-109">Weitere Informationen finden Sie unter [erstellen und Bearbeiten typisierter Datasets](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets).</span><span class="sxs-lookup"><span data-stu-id="567c2-109">For more information, see [Creating and Editing Typed Datasets](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="567c2-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="567c2-110">To correct this error</span></span>  
  
-   <span data-ttu-id="567c2-111">Überprüfen Sie, ob Sie den richtigen Dateinamen angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="567c2-111">Check that you are supplying the correct file name.</span></span>  
  
-   <span data-ttu-id="567c2-112">Überprüfen Sie, ob die angegebene Datei gültiges XML enthält, indem Sie die zu überprüfende XML-Datei im **XML-Designer**laden.</span><span class="sxs-lookup"><span data-stu-id="567c2-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="567c2-113">Klicken Sie im Menü **XML** auf **XML überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="567c2-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="567c2-114">Fehler werden im Fenster **Aufgabenliste**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="567c2-114">Errors are displayed in the **Task List**.</span></span>  
  
-   <span data-ttu-id="567c2-115">Wenn der XML-Datei ein XML-Schema zugeordnet ist, überprüfen Sie, ob die Elemente in der definierten Struktur angezeigt werden und der Inhalt der einzelnen Elemente den im Schema angegebenen deklarierten Datentypen entspricht.</span><span class="sxs-lookup"><span data-stu-id="567c2-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="567c2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="567c2-116">See Also</span></span>  
 <span data-ttu-id="567c2-117"><xref:System.Xml></xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="567c2-117"><xref:System.Xml></span></span>   
<span data-ttu-id="567c2-118"> [Gewusst wie: Analysieren von Dateipfaden](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)</span><span class="sxs-lookup"><span data-stu-id="567c2-118"> [How to: Parse File Paths](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)</span></span>
