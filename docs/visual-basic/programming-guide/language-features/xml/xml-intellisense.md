---
title: "IntelliSense für XML in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, XML
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: 59506ce9-d64e-417e-90fc-e9fe19f0a8fa
caps.latest.revision: 27
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
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 9a3c6f923bc9458997c388d4cf74ca113265a8cc
ms.contentlocale: de-de
ms.lasthandoff: 06/01/2017

---
# <a name="xml-intellisense-in-visual-basic"></a><span data-ttu-id="4be70-102">XML IntelliSense in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4be70-102">XML IntelliSense in Visual Basic</span></span>
<span data-ttu-id="4be70-103">Der Visual Basic-Code-Editor enthält die IntelliSense-Funktionen für XML, die Word-Abschluss in ein XML-Schema definierte Elemente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4be70-103">The Visual Basic Code Editor includes IntelliSense features for XML that provide word completion for elements defined in an XML schema.</span></span> <span data-ttu-id="4be70-104">Wenn Sie eine XML-Schema Definition (XSD)-Datei in Ihrem Projekt hinzugefügt, und importieren den Zielnamespace des Schemas mithilfe der `Imports` -Anweisung, die Code-Editor enthält Elemente aus dem XSD-Schema in der IntelliSense-Liste der gültigen Membervariablen für <xref:System.Xml.Linq.XElement>und <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="4be70-104">If you include an XML Schema Definition (XSD) file in your project and import the target namespace of the schema by using the `Imports` statement, the Code Editor will include elements from the XSD schema in the IntelliSense list of valid member variables for <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="4be70-105">Die folgende Abbildung zeigt die IntelliSense-Memberliste für ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="4be70-105">The following illustration shows the IntelliSense members list for an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="4be70-106">![IntelliSense für XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")</span><span class="sxs-lookup"><span data-stu-id="4be70-106">![XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")</span></span>  
<span data-ttu-id="4be70-107">IntelliSense für XML</span><span class="sxs-lookup"><span data-stu-id="4be70-107">XML IntelliSense</span></span>  
  
## <a name="enabling-xml-intellisense-in-visual-basic"></a><span data-ttu-id="4be70-108">Aktivieren von IntelliSense für XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4be70-108">Enabling XML IntelliSense in Visual Basic</span></span>  
 <span data-ttu-id="4be70-109">Um IntelliSense für XML in Visual Basic zu aktivieren, müssen Sie in Visual Basic-Projekt eine XSD-Schemadatei einschließen.</span><span class="sxs-lookup"><span data-stu-id="4be70-109">To enable XML IntelliSense in Visual Basic, you must include an XSD schema file in your Visual Basic project.</span></span> <span data-ttu-id="4be70-110">Sie müssen auch den Zielnamespace für das XSD-Schema in die Codedatei importieren, mit der `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4be70-110">You must also import the target namespace for the XSD schema into your code file by using the `Imports` statement.</span></span> <span data-ttu-id="4be70-111">Alternativ können Sie den Zielnamespace auch die Liste der Namespaces auf Projektebene hinzufügen, mit der **Verweise** im Visual Basic-Projekt-Designer auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="4be70-111">Alternatively, you can add the target namespace to the project-level namespace list by using the **References** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="4be70-112">Beispiele finden Sie unter [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="4be70-112">For examples, see [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span></span> <span data-ttu-id="4be70-113">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) und [Seite "Verweise", Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4be70-113">For more information, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) and [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="4be70-114">Beachten Sie, die standardmäßig nicht XSD-Schemadateien in Visual Basic-Projekte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be70-114">Note that by default you cannot see XSD schema files in Visual Basic projects.</span></span> <span data-ttu-id="4be70-115">Möglicherweise müssen Sie klicken Sie auf die **alle Dateien anzeigen** klicken, um eine XSD-Datei in Ihr Projekt aufnehmen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4be70-115">You may have to click the **Show All Files** button to select an XSD file to include in your project.</span></span>  
  
### <a name="generating-a-schema-file-schema-inference"></a><span data-ttu-id="4be70-116">Generieren einer Schemadatei (Schemarückschluss)</span><span class="sxs-lookup"><span data-stu-id="4be70-116">Generating a Schema File (Schema Inference)</span></span>  
 <span data-ttu-id="4be70-117">Sie können ein XSD-Schema für eine vorhandene XML-Datei anhand des XSD-Schemas mithilfe von Visual Studio-XML-Tools erstellen.</span><span class="sxs-lookup"><span data-stu-id="4be70-117">You can create an XSD schema for an existing XML file by inferring the XSD schema by using Visual Studio XML tools.</span></span>  
  
-   <span data-ttu-id="4be70-118">Ab SP1 können Sie das XML to Schema-Assistenten ein XML-Schemaset abgeleitet wird von ein oder mehrere XML-Dokumente erstellen und es in das Projekt integrieren.</span><span class="sxs-lookup"><span data-stu-id="4be70-118">Starting in SP1, you can use the XML to Schema Wizard to create an XML Schema set that is inferred from one or more XML documents and include it your project.</span></span> <span data-ttu-id="4be70-119">Sie können eine beliebige Kombination von XML-Dokumenten in Form von Textdateien, XML aus HTTP-Internetadressen oder XML, das Eingabe oder beim Einfügen in das XML-Schema-Assistenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4be70-119">You can use any combination of XML documents in the form of text files, XML from HTTP Internet addresses, or XML that is typed or pasted into the XML to Schema Wizard.</span></span> <span data-ttu-id="4be70-120">Um das XML to Schema-Assistenten zuzugreifen, klicken Sie auf **neues Element hinzufügen** auf der **Projekt** Menü und fügen eine **XML zu Schema** Vorlage aus der **Daten** oder **gemeinsame Elemente** Vorlagengruppe.</span><span class="sxs-lookup"><span data-stu-id="4be70-120">To access the XML to Schema Wizard, click **Add New Item** on the **Project** menu and add an **XML to Schema** template from either the **Data** or **Common Items** template group.</span></span> <span data-ttu-id="4be70-121">Nachdem Sie alle der XML-Dokumentquellen aus der XML-Schemaset hinzugefügt haben, klicken Sie auf **OK** das hergeleitete Schema zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4be70-121">After you have included all the XML document sources to infer the XML Schema set from, click **OK** to create the inferred schema set.</span></span> <span data-ttu-id="4be70-122">Weitere Informationen finden Sie unter [XML-Schema-Assistenten](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4be70-122">For more information, see [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).</span></span>  
  
-   <span data-ttu-id="4be70-123">Sie können auch XML-Editor von Visual Studio verwenden, Herleiten ein XSD-Schemas aus einer XML-Datei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4be70-123">You can also use the Visual Studio XML Editor to infer an XSD schema set from an XML file.</span></span> <span data-ttu-id="4be70-124">Um ein XML-Schemaset im XML-Editor zu erstellen, öffnen Sie eine XML-Datei im XML-Designer von Visual Studio, und klicken Sie dann auf **Create Schema** auf der **XML** Menü.</span><span class="sxs-lookup"><span data-stu-id="4be70-124">To create an XML schema set by using the XML Editor, open an XML file in the Visual Studio XML Designer and then click **Create Schema** on the **XML** menu.</span></span> <span data-ttu-id="4be70-125">Nachdem Sie die XSD-Schema erstellen, können Sie erstellte Schemaset in eine oder mehrere XSD-Dateien speichern und in Ihr Projekt einbinden.</span><span class="sxs-lookup"><span data-stu-id="4be70-125">After you create the XSD schema set, you can save the created schema set to one or more XSD files and include them in your project.</span></span> <span data-ttu-id="4be70-126">Weitere Informationen finden Sie unter[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="4be70-126">For more information, see[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span></span>  
  
 <span data-ttu-id="4be70-127">Beachten Sie, dass unterschiedliche Sätze von XSD-Schemas von mehreren XML-Dokumenten abgeleitet sein können, die das gleiche Schema aufweisen sollen.</span><span class="sxs-lookup"><span data-stu-id="4be70-127">Note that different XSD schema sets might be inferred from multiple XML documents that are intended to have the same schema.</span></span> <span data-ttu-id="4be70-128">Dies kann auftreten, wenn bestimmte Elemente und Attribute in einer XML-Datei und nicht in einem anderen gefunden werden, oder wenn Elemente in verschiedenen Reihenfolgen enthalten sind, z. B..</span><span class="sxs-lookup"><span data-stu-id="4be70-128">This can occur when particular elements and attributes are found in one XML file and not in another, or when elements are included in different order, for example.</span></span> <span data-ttu-id="4be70-129">Wenn Sie XSD-Schemarückschluss verwenden, sollten Sie abgeleiteten XSD-Schemasets auf Vollständigkeit und Richtigkeit überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4be70-129">You should review inferred XSD schema sets for completeness and accuracy when you use XSD schema inference.</span></span>  
  
## <a name="member-list"></a><span data-ttu-id="4be70-130">Mitgliederliste</span><span class="sxs-lookup"><span data-stu-id="4be70-130">Member List</span></span>  
 <span data-ttu-id="4be70-131">Nach der Eingabe von eines Punkts (.) zum Trennen von einer Instanz von einer <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>Objekt (oder eine Instanz von `IEnumerable(Of XElement)` oder `IEnumerable(Of XDocument)`), Visual Basic IntelliSense zeigt eine Liste der möglichen Objektmember.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="4be70-131">After you type a period (.) to delimit an instance of an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object (or an instance of `IEnumerable(Of XElement)` or `IEnumerable(Of XDocument)`), Visual Basic IntelliSense displays a list of possible object members.</span></span> <span data-ttu-id="4be70-132">Die anfängliche Liste enthält drei Optionen, die XML-Achseneigenschaften darstellen, wie in der folgenden Liste beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4be70-132">The initial list includes three options that represent XML axis properties, as described in the following list.</span></span>  
  
|<span data-ttu-id="4be70-133">Option</span><span class="sxs-lookup"><span data-stu-id="4be70-133">Option</span></span>|<span data-ttu-id="4be70-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4be70-134">Description</span></span>|  
|---|---|  
|**\< >**|<span data-ttu-id="4be70-135">Wählen Sie diese Option, um eine Liste der möglichen untergeordneten Elemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4be70-135">Select this option to show a list of possible child elements.</span></span> <span data-ttu-id="4be70-136">Weitere Informationen finden Sie unter [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und der <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="4be70-136">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>|  
|**@**|<span data-ttu-id="4be70-137">Wählen Sie diese Option, um eine Liste der möglichen Attribute anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4be70-137">Select this option to show a list of possible attributes.</span></span> <span data-ttu-id="4be70-138">Weitere Informationen finden Sie unter [XML-Achseneigenschaften](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md). Diese Option steht nur für Objekte vom Typ <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="4be70-138">For more information, see [XML Axis Properties](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).This option is available only for objects of type <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="4be70-139">**…\< >**</span><span class="sxs-lookup"><span data-stu-id="4be70-139">**…\< >**</span></span>|<span data-ttu-id="4be70-140">Wählen Sie diese Option, um eine Liste der möglichen untergeordneten Elemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4be70-140">Select this option to show a list of possible descendant elements.</span></span> <span data-ttu-id="4be70-141">Weitere Informationen finden Sie unter [Gewusst wie: Zugriff auf XML-Nachfolger Elemente](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) und die <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="4be70-141">For more information, see [How to: Access XML Descendant Elements](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) and the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>|  
  
 <span data-ttu-id="4be70-142">Wählen Sie aus, oder beginnen Sie, geben Sie die XML-Optionen aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="4be70-142">Select or begin typing any of the XML options from the list.</span></span> <span data-ttu-id="4be70-143">Die Memberliste wird potenzielle Member aus dem XML-Schema angezeigt, die für die ausgewählte Option spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="4be70-143">The member list will then display potential members from the XML schema that are specific to the selected option.</span></span> <span data-ttu-id="4be70-144">Wenn Sie XML-Namespaces importiert, die einem bestimmten XML-Namespace-Präfix zugeordnet sind haben, ist eine Liste der potenziellen XML-Namespacepräfixe in der Memberliste enthalten.</span><span class="sxs-lookup"><span data-stu-id="4be70-144">If you have XML namespaces imported that are associated with a specific XML namespace prefix, a list of potential XML namespace prefixes is included in the member list.</span></span>  
  
 <span data-ttu-id="4be70-145">Betrachten Sie beispielsweise das folgende XSD-Schema.</span><span class="sxs-lookup"><span data-stu-id="4be70-145">For example, consider the following XSD schema.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema attributeFormDefault="unqualified"   
           elementFormDefault="qualified"   
           targetNamespace="http://SamplePurchaseOrder"   
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="PurchaseOrders">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="PurchaseOrder">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="Address" />  
              <xs:element name="Items" />  
              <xs:element name="Comment" />  
            </xs:sequence>  
            <xs:attribute name="PurchaseOrderNumber" type="xs:unsignedShort" use="required" />  
            <xs:attribute name="OrderDate" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="4be70-146">Gültiges XML für das XSD-Schema würde wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="4be70-146">Valid XML for the XSD schema would resemble the following.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<PurchaseOrders xmlns="http://SamplePurchaseOrder">  
  <PurchaseOrder PurchaseOrderNumber="12345" OrderDate="2000-1-1">  
    <Address />  
    <Items />  
    <Comment />  
  </PurchaseOrder>  
</PurchaseOrders>  
```  
  
 <span data-ttu-id="4be70-147">Wenn Sie diese XSD-Schema-Datei in einem Projekt einschließen und den Zielnamespace aus dem XSD-Schema in die Codedatei oder das Projekt importieren, werden Visual Basic IntelliSense während der Eingabe von Visual Basic-Code Member aus dem Schema angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be70-147">If you include this XSD schema file in a project and import the target namespace from the XSD schema into your code file or project, Visual Basic IntelliSense displays members from the schema as you type your Visual Basic code.</span></span> <span data-ttu-id="4be70-148">Wenn der Zielnamespace für das XSD-Schema als Standardnamespace importiert wird, und geben Sie Folgendes ein, zeigt IntelliSense eine Liste der möglichen untergeordneten Elemente für die `PurchaseOrder` -XML-Element.</span><span class="sxs-lookup"><span data-stu-id="4be70-148">If the target namespace for the XSD schema is imported as the default namespace and you type the following, IntelliSense displays a list of possible child elements for the `PurchaseOrder` XML element.</span></span>  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 <span data-ttu-id="4be70-149">Die Liste besteht aus den Elementen Adresse, Kommentieren und Elemente.</span><span class="sxs-lookup"><span data-stu-id="4be70-149">The list consists of the Address, Comment, and Items elements.</span></span>  
  
### <a name="certainty-levels-for-intellisense-list-items"></a><span data-ttu-id="4be70-150">Wahrscheinlichkeitsstufen für IntelliSense-Listenelemente</span><span class="sxs-lookup"><span data-stu-id="4be70-150">Certainty Levels for IntelliSense List Items</span></span>  
 <span data-ttu-id="4be70-151">Bestimmen die XSD-Typ für IntelliSense ist nicht exakt.</span><span class="sxs-lookup"><span data-stu-id="4be70-151">Determining the XSD type to use for IntelliSense is not exact.</span></span> <span data-ttu-id="4be70-152">Daher wird IntelliSense für XML häufig eine umfangreichere Liste der möglichen Elemente angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be70-152">As a result, XML IntelliSense will often show an expanded list of possible members.</span></span> <span data-ttu-id="4be70-153">Als Hilfe für das Auswählen eines Elements aus der IntelliSense-Memberliste werden Elemente mit einem Indikator für die Wahrscheinlichkeit angezeigt, die XML IntelliSense für einen bestimmten Member verfügt.</span><span class="sxs-lookup"><span data-stu-id="4be70-153">To aid you in selecting an item from the IntelliSense member list, items are displayed with an indication of the level of certainty that XML IntelliSense has for a particular member.</span></span>  
  
 <span data-ttu-id="4be70-154">Manchmal kann IntelliSense für XML einen bestimmten Typ aus dem XSD-Schema identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4be70-154">Sometimes XML IntelliSense can identify a specific type from the XSD schema.</span></span> <span data-ttu-id="4be70-155">In diesen Fällen wird mögliche untergeordnete Elemente, Attribute oder Nachfolgerelemente für diesen XSD-Typ mit hoher Wahrscheinlichkeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be70-155">In these cases, it will display possible child elements, attributes, or descendant elements for that XSD type with a high degree of certainty.</span></span> <span data-ttu-id="4be70-156">Diese Elemente werden mit einem Häkchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="4be70-156">These items are identified with a check mark.</span></span>  
  
 <span data-ttu-id="4be70-157">Allerdings kann manchmal XML IntelliSense nicht zur Identifizierung eines bestimmten Typs aus dem XSD-Schema.</span><span class="sxs-lookup"><span data-stu-id="4be70-157">However, sometimes XML IntelliSense is not able to identify a specific type from the XSD schema.</span></span> <span data-ttu-id="4be70-158">In diesen Fällen wird eine umfangreichere Liste der möglichen untergeordneten Elemente, Attribute oder untergeordneten Elemente aus dem XSD-Schema für das Projekt mit einer geringeren Wahrscheinlichkeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be70-158">In these cases, it will display an expanded list of possible child elements, attributes, or descendant elements from the XSD schema for the project with a low degree of certainty.</span></span> <span data-ttu-id="4be70-159">Diese Elemente werden mit einem Fragezeichen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="4be70-159">These items are identified with a question mark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be70-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4be70-160">See Also</span></span>  
 <span data-ttu-id="4be70-161">[Gewusst wie: Aktivieren von XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md) </span><span class="sxs-lookup"><span data-stu-id="4be70-161">[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md) </span></span>  
<span data-ttu-id="4be70-162"> [XML-Schema-Assistenten](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="4be70-162"> [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md) </span></span>  
<span data-ttu-id="4be70-163"> [Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="4be70-163"> [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="4be70-164"> [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="4be70-164"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="4be70-165"> [XML-Attributachseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="4be70-165"> [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span></span>  
<span data-ttu-id="4be70-166"> [XML-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="4be70-166"> [XML Descendant Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md) </span></span>  
<span data-ttu-id="4be70-167"> [Seite „Verweise“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="4be70-167"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span></span>
