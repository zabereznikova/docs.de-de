---
title: "Einlesen von Entitätsdeklarationen und Entitätsverweisen in das Dokumentobjektmodell"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86dba977-5cc4-4567-964f-027ffabc47b2
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6370db06cbe7ff8d46258b0315059f5c37587fea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a><span data-ttu-id="e71a6-102">Einlesen von Entitätsdeklarationen und Entitätsverweisen in das Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="e71a6-102">Reading Entity Declarations and Entity References into the DOM</span></span>
<span data-ttu-id="e71a6-103">Eine Entität ist eine Deklaration, die einen Namen angibt, der anstelle von Inhalt oder Markup im XML-Code zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="e71a6-103">An entity is a declaration that states a name to be used in the XML in place of content or markup.</span></span> <span data-ttu-id="e71a6-104">Entitäten setzen sich aus zwei Teilen zusammen.</span><span class="sxs-lookup"><span data-stu-id="e71a6-104">There are two parts to entities.</span></span> <span data-ttu-id="e71a6-105">Erstens müssen Sie mithilfe einer Entitätsdeklaration einen Namen an den ersetzenden Inhalt binden.</span><span class="sxs-lookup"><span data-stu-id="e71a6-105">First, you must tie a name to the replacement content using an entity declaration.</span></span> <span data-ttu-id="e71a6-106">Eine Entitätsdeklaration wird durch Verwenden der `<!ENTITY name "value">`-Syntax in einer DTD (Document Type Definition) oder einem XML-Schema erstellt.</span><span class="sxs-lookup"><span data-stu-id="e71a6-106">An entity declaration is created by using the `<!ENTITY name "value">` syntax in a document type definition (DTD) or XML schema.</span></span> <span data-ttu-id="e71a6-107">Zweitens wird der Name, der in der Entitätsdeklaration definiert wurde, anschließend im XML-Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="e71a6-107">Secondly, the name defined in the entity declaration is subsequently used in the XML.</span></span> <span data-ttu-id="e71a6-108">Bei der Verwendung im XML-Code wird dieser Name als Entitätsverweis bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e71a6-108">When used in the XML, it is called an entity reference.</span></span> <span data-ttu-id="e71a6-109">Die folgende Entitätsdeklaration deklariert z. B., dass eine Entität mit dem Namen `publisher` mit dem Inhalt von "Microsoft Press" verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="e71a6-109">For example, the following entity declaration declares an entity of the name `publisher` being associated with the content of "Microsoft Press".</span></span>  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 <span data-ttu-id="e71a6-110">Im folgenden Beispiel wird die Verwendung dieser Entitätsdeklaration im XML-Code als Entitätsverweis veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e71a6-110">The following example shows the use of this entity declaration in XML as an entity reference.</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="e71a6-111">Manche Parser erweitern Entitäten automatisch, wenn ein Dokument in den Speicher geladen wird.</span><span class="sxs-lookup"><span data-stu-id="e71a6-111">Some parsers automatically expand entities when a document is loaded into memory.</span></span> <span data-ttu-id="e71a6-112">Daher werden Entitätsdeklarationen, wenn der XML-Code in den Speicher eingelesen wird, aufbewahrt und gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e71a6-112">Therefore, when the XML is being read into memory, entity declarations are remembered and saved.</span></span> <span data-ttu-id="e71a6-113">Wenn der Parser anschließend auf `&;`-Zeichen stößt, die einen allgemeinen Entitätsverweis kennzeichnen, sucht der Parser diesen Namen in einer Entitätsdeklarationstabelle.</span><span class="sxs-lookup"><span data-stu-id="e71a6-113">When the parser subsequently encounters `&;` characters, which identify a general entity reference, the parser looks up that name in an entity declaration table.</span></span> <span data-ttu-id="e71a6-114">Der Verweis, `&publisher;`, wird durch den entsprechenden Inhalt ersetzt.</span><span class="sxs-lookup"><span data-stu-id="e71a6-114">The reference, `&publisher;` is replaced by the content that it represents.</span></span> <span data-ttu-id="e71a6-115">Bei dem folgenden XML-Code</span><span class="sxs-lookup"><span data-stu-id="e71a6-115">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="e71a6-116">, das Erweitern des Entitätsverweises und das Ersetzen von `&publisher;` durch "Microsoft Press" führt zu folgendem erweiterten XML-Code.</span><span class="sxs-lookup"><span data-stu-id="e71a6-116">expanding the entity reference and replacing the `&publisher;` with the Microsoft Press content gives the following expanded XML.</span></span>  
  
 <span data-ttu-id="e71a6-117">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="e71a6-117">**Output**</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 <span data-ttu-id="e71a6-118">Es gibt viele verschiedene Entitäten.</span><span class="sxs-lookup"><span data-stu-id="e71a6-118">There are many kinds of entities.</span></span> <span data-ttu-id="e71a6-119">Die folgende Abbildung zeigt die einzelnen Entitätstypen und die zugehörige Terminologie.</span><span class="sxs-lookup"><span data-stu-id="e71a6-119">The following diagram shows the breakdown of entity types and terminology.</span></span>  
  
 <span data-ttu-id="e71a6-120">![Flussdiagramm für entitätstyphierarchie](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="e71a6-120">![flow chart of entity type hierarchy](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span></span>  
  
 <span data-ttu-id="e71a6-121">Die Standardeinstellung für die Microsoft .NET Framework-Implementierung des XML-Dokument Objekt Model (DOM) werden von Entitätsverweise beibehalten und die Entitäten nicht erweitert werden, wenn der XML-Code geladen wird.</span><span class="sxs-lookup"><span data-stu-id="e71a6-121">The default for the Microsoft .NET Framework implementation of the XML Document Object Model (DOM) is to preserve the entities references and not expand the entities when the XML is loaded.</span></span> <span data-ttu-id="e71a6-122">Die Implikation hiervon erfolgt, die wie ein Dokument in das DOM geladen wird ein **XmlEntityReference** Knoten mit die Verweisvariable `&publisher;` mit untergeordneten Knoten, die den Inhalt in der Entität darstellt, die in der DTD deklarierte, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e71a6-122">The implication of this is that as a document is loaded in the DOM, an **XmlEntityReference** node containing the reference variable `&publisher;` is created, with child nodes representing the content in the entity declared in the DTD.</span></span>  
  
 <span data-ttu-id="e71a6-123">Mithilfe der `<!ENTITY publisher "Microsoft Press">` Entitätsdeklaration, das folgende Diagramm zeigt die **XmlEntity** und **XmlText** Knoten, die anhand der Entitätsdeklaration erstellt.</span><span class="sxs-lookup"><span data-stu-id="e71a6-123">Using the `<!ENTITY publisher "Microsoft Press">` entity declaration, the following diagram shows the **XmlEntity** and **XmlText** nodes created from this declaration.</span></span>  
  
 <span data-ttu-id="e71a6-124">![Knoten, die aus Entitätsdeklarationen erstellt](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span><span class="sxs-lookup"><span data-stu-id="e71a6-124">![nodes created from entity declaration](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span></span>  
  
 <span data-ttu-id="e71a6-125">Die Tatsache, ob Entitätsverweise erweitert werden oder nicht, ist entscheidend dafür, welche Knoten in der DOM-Struktur im Speicher generiert werden.</span><span class="sxs-lookup"><span data-stu-id="e71a6-125">The differences when entity references are expanded and when they are not makes a difference in what nodes are generated in the DOM tree, in memory.</span></span> <span data-ttu-id="e71a6-126">Die Unterschiede zwischen den Knoten, die generiert werden, wird in den Themen erläutert [Entitätsverweise werden beibehalten](../../../../docs/standard/data/xml/entity-references-are-preserved.md) und [Entitätsverweise werden erweitert und nicht beibehalten](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span><span class="sxs-lookup"><span data-stu-id="e71a6-126">The difference in the nodes that are generated is explained in the topics [Entity References are Preserved](../../../../docs/standard/data/xml/entity-references-are-preserved.md) and [Entity References are Expanded and Not Preserved](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e71a6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e71a6-127">See Also</span></span>  
 [<span data-ttu-id="e71a6-128">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="e71a6-128">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
