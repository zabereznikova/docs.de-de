---
title: Die in „Dateiname“ angegebene Datei ist keine gültige XML-Datei.
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: d4babe81f950bcf9b23d053405fb293e81056c36
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582095"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="16d43-102">Die in „Dateiname“ angegebene Datei ist keine gültige XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="16d43-102">File specified in FileName is not a valid XML file</span></span>
<span data-ttu-id="16d43-103">Der von Ihnen angegebene Dateiname gehört nicht zu einer gültigen XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="16d43-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="16d43-104">Sie können eine Dokumenttypdefinition (DTD), ein Microsoft XDR-Schemaformat (XML-Data Reduced) oder ein XSD-Schema (Sprache der XML-Schemadefinition) verwenden, um die zulässige Struktur und die Inhalte eines XML-Dokuments anzugeben.</span><span class="sxs-lookup"><span data-stu-id="16d43-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="16d43-105">XSD-Schemas sind die bevorzugte Methode zum Angeben von XML-Grammatiken im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16d43-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>

> [!NOTE]
>  <span data-ttu-id="16d43-106">In einigen früheren Versionen von Visual Studio stellt der **XML-Designer** den Designer für typisierte DataSets und XML-Schemas dar.</span><span class="sxs-lookup"><span data-stu-id="16d43-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="16d43-107">Der **XML-Designer** kann weiterhin zum Erstellen und Bearbeiten von XML-Schemadateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="16d43-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="16d43-108">In Visual Studio 2012 ist der Designer zum Erstellen und Bearbeiten typisierter Datasets jedoch die **Dataset-Designer**.</span><span class="sxs-lookup"><span data-stu-id="16d43-108">However, in Visual Studio 2012, the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="16d43-109">Weitere Informationen finden Sie unter [erstellen und Bearbeiten typisierter Datasets](/visualstudio/data-tools/creating-and-editing-typed-datasets).</span><span class="sxs-lookup"><span data-stu-id="16d43-109">For more information, see [Creating and Editing Typed Datasets](/visualstudio/data-tools/creating-and-editing-typed-datasets).</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="16d43-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="16d43-110">To correct this error</span></span>

-   <span data-ttu-id="16d43-111">Überprüfen Sie, ob Sie den richtigen Dateinamen angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="16d43-111">Check that you are supplying the correct file name.</span></span>

-   <span data-ttu-id="16d43-112">Überprüfen Sie, ob die angegebene Datei gültiges XML enthält, indem Sie die zu überprüfende XML-Datei im **XML-Designer**laden.</span><span class="sxs-lookup"><span data-stu-id="16d43-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="16d43-113">Klicken Sie im Menü **XML** auf **XML überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="16d43-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="16d43-114">Fehler werden im Fenster **Aufgabenliste**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="16d43-114">Errors are displayed in the **Task List**.</span></span>

-   <span data-ttu-id="16d43-115">Wenn der XML-Datei ein XML-Schema zugeordnet ist, überprüfen Sie, ob die Elemente in der definierten Struktur angezeigt werden und der Inhalt der einzelnen Elemente den im Schema angegebenen deklarierten Datentypen entspricht.</span><span class="sxs-lookup"><span data-stu-id="16d43-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>

## <a name="see-also"></a><span data-ttu-id="16d43-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16d43-116">See Also</span></span>

- <xref:System.Xml>
- [<span data-ttu-id="16d43-117">Gewusst wie: Analysieren von Dateipfaden</span><span class="sxs-lookup"><span data-stu-id="16d43-117">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)