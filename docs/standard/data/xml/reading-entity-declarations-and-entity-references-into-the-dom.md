---
title: Einlesen von Entitätsdeklarationen und Entitätsverweisen in das Dokumentobjektmodell
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 86dba977-5cc4-4567-964f-027ffabc47b2
ms.openlocfilehash: fa650e75d7661eeafea74146f5cbb61878978575
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710400"
---
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a><span data-ttu-id="f61a2-102">Einlesen von Entitätsdeklarationen und Entitätsverweisen in das Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="f61a2-102">Reading Entity Declarations and Entity References into the DOM</span></span>
<span data-ttu-id="f61a2-103">Eine Entität ist eine Deklaration, die einen Namen angibt, der anstelle von Inhalt oder Markup im XML-Code zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="f61a2-103">An entity is a declaration that states a name to be used in the XML in place of content or markup.</span></span> <span data-ttu-id="f61a2-104">Entitäten setzen sich aus zwei Teilen zusammen.</span><span class="sxs-lookup"><span data-stu-id="f61a2-104">There are two parts to entities.</span></span> <span data-ttu-id="f61a2-105">Erstens müssen Sie mithilfe einer Entitätsdeklaration einen Namen an den ersetzenden Inhalt binden.</span><span class="sxs-lookup"><span data-stu-id="f61a2-105">First, you must tie a name to the replacement content using an entity declaration.</span></span> <span data-ttu-id="f61a2-106">Eine Entitätsdeklaration wird durch Verwenden der `<!ENTITY name "value">`-Syntax in einer DTD (Document Type Definition) oder einem XML-Schema erstellt.</span><span class="sxs-lookup"><span data-stu-id="f61a2-106">An entity declaration is created by using the `<!ENTITY name "value">` syntax in a document type definition (DTD) or XML schema.</span></span> <span data-ttu-id="f61a2-107">Zweitens wird der Name, der in der Entitätsdeklaration definiert wurde, anschließend im XML-Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="f61a2-107">Secondly, the name defined in the entity declaration is subsequently used in the XML.</span></span> <span data-ttu-id="f61a2-108">Bei der Verwendung im XML-Code wird dieser Name als Entitätsverweis bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f61a2-108">When used in the XML, it is called an entity reference.</span></span> <span data-ttu-id="f61a2-109">Die folgende Entitätsdeklaration deklariert z. B., dass eine Entität mit dem Namen `publisher` mit dem Inhalt von "Microsoft Press" verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="f61a2-109">For example, the following entity declaration declares an entity of the name `publisher` being associated with the content of "Microsoft Press".</span></span>  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 <span data-ttu-id="f61a2-110">Im folgenden Beispiel wird die Verwendung dieser Entitätsdeklaration im XML-Code als Entitätsverweis veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f61a2-110">The following example shows the use of this entity declaration in XML as an entity reference.</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="f61a2-111">Manche Parser erweitern Entitäten automatisch, wenn ein Dokument in den Speicher geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f61a2-111">Some parsers automatically expand entities when a document is loaded into memory.</span></span> <span data-ttu-id="f61a2-112">Daher werden Entitätsdeklarationen, wenn der XML-Code in den Speicher eingelesen wird, aufbewahrt und gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f61a2-112">Therefore, when the XML is being read into memory, entity declarations are remembered and saved.</span></span> <span data-ttu-id="f61a2-113">Wenn der Parser anschließend auf `&;`-Zeichen stößt, die einen allgemeinen Entitätsverweis kennzeichnen, sucht der Parser diesen Namen in einer Entitätsdeklarationstabelle.</span><span class="sxs-lookup"><span data-stu-id="f61a2-113">When the parser subsequently encounters `&;` characters, which identify a general entity reference, the parser looks up that name in an entity declaration table.</span></span> <span data-ttu-id="f61a2-114">Der Verweis, `&publisher;`, wird durch den entsprechenden Inhalt ersetzt.</span><span class="sxs-lookup"><span data-stu-id="f61a2-114">The reference, `&publisher;` is replaced by the content that it represents.</span></span> <span data-ttu-id="f61a2-115">Bei dem folgenden XML-Code</span><span class="sxs-lookup"><span data-stu-id="f61a2-115">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="f61a2-116">, das Erweitern des Entitätsverweises und das Ersetzen von `&publisher;` durch "Microsoft Press" führt zu folgendem erweiterten XML-Code.</span><span class="sxs-lookup"><span data-stu-id="f61a2-116">expanding the entity reference and replacing the `&publisher;` with the Microsoft Press content gives the following expanded XML.</span></span>  
  
 <span data-ttu-id="f61a2-117">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="f61a2-117">**Output**</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 <span data-ttu-id="f61a2-118">Es gibt viele verschiedene Entitäten.</span><span class="sxs-lookup"><span data-stu-id="f61a2-118">There are many kinds of entities.</span></span> <span data-ttu-id="f61a2-119">Die folgende Abbildung zeigt die einzelnen Entitätstypen und die zugehörige Terminologie.</span><span class="sxs-lookup"><span data-stu-id="f61a2-119">The following diagram shows the breakdown of entity types and terminology.</span></span>  
  
 <span data-ttu-id="f61a2-120">![Flussdiagramm für Entitätstyphierarchie](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="f61a2-120">![flow chart of entity type hierarchy](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span></span>  
  
 <span data-ttu-id="f61a2-121">Für die .NET Framework-Implementierung des Dokumentobjektmodells (DOM) werden die Entitätsverweise standardmäßig beibehalten, und die Entitäten werden nicht erweitert, wenn der XML-Code geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f61a2-121">The default for the Microsoft .NET Framework implementation of the XML Document Object Model (DOM) is to preserve the entities references and not expand the entities when the XML is loaded.</span></span> <span data-ttu-id="f61a2-122">Dies hat folgende Konsequenzen: Wenn ein Dokument in das DOM geladen wird, wird ein **XmlEntityReference**-Knoten erstellt, der die Verweisvariable `&publisher;` enthält. Dieser Knoten enthält untergeordnete Knoten, die den Inhalt der in der DTD deklarierten Entität darstellen.</span><span class="sxs-lookup"><span data-stu-id="f61a2-122">The implication of this is that as a document is loaded in the DOM, an **XmlEntityReference** node containing the reference variable `&publisher;` is created, with child nodes representing the content in the entity declared in the DTD.</span></span>  
  
 <span data-ttu-id="f61a2-123">Im folgenden Diagramm werden die Knoten **XmlEntity** und **XmlText** dargestellt, die anhand der Entitätsdeklaration `<!ENTITY publisher "Microsoft Press">` erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f61a2-123">Using the `<!ENTITY publisher "Microsoft Press">` entity declaration, the following diagram shows the **XmlEntity** and **XmlText** nodes created from this declaration.</span></span>  
  
 <span data-ttu-id="f61a2-124">![Knoten, die aus Entitätsdeklarationen erstellt werden](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span><span class="sxs-lookup"><span data-stu-id="f61a2-124">![nodes created from entity declaration](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span></span>  
  
 <span data-ttu-id="f61a2-125">Die Tatsache, ob Entitätsverweise erweitert werden oder nicht, ist entscheidend dafür, welche Knoten in der DOM-Struktur im Speicher generiert werden.</span><span class="sxs-lookup"><span data-stu-id="f61a2-125">The differences when entity references are expanded and when they are not makes a difference in what nodes are generated in the DOM tree, in memory.</span></span> <span data-ttu-id="f61a2-126">Die Unterschiede zwischen den generierten Knoten werden in den Themen [Entitätsverweise werden beibehalten](../../../../docs/standard/data/xml/entity-references-are-preserved.md) und [Entitätsverweise werden erweitert und nicht beibehalten](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md) erläutert.</span><span class="sxs-lookup"><span data-stu-id="f61a2-126">The difference in the nodes that are generated is explained in the topics [Entity References are Preserved](../../../../docs/standard/data/xml/entity-references-are-preserved.md) and [Entity References are Expanded and Not Preserved](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f61a2-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f61a2-127">See also</span></span>

- [<span data-ttu-id="f61a2-128">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="f61a2-128">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
