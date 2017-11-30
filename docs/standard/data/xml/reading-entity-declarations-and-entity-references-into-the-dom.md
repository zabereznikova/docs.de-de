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
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a>Einlesen von Entitätsdeklarationen und Entitätsverweisen in das Dokumentobjektmodell
Eine Entität ist eine Deklaration, die einen Namen angibt, der anstelle von Inhalt oder Markup im XML-Code zu verwenden ist. Entitäten setzen sich aus zwei Teilen zusammen. Erstens müssen Sie mithilfe einer Entitätsdeklaration einen Namen an den ersetzenden Inhalt binden. Eine Entitätsdeklaration wird durch Verwenden der `<!ENTITY name "value">`-Syntax in einer DTD (Document Type Definition) oder einem XML-Schema erstellt. Zweitens wird der Name, der in der Entitätsdeklaration definiert wurde, anschließend im XML-Code verwendet. Bei der Verwendung im XML-Code wird dieser Name als Entitätsverweis bezeichnet. Die folgende Entitätsdeklaration deklariert z. B., dass eine Entität mit dem Namen `publisher` mit dem Inhalt von "Microsoft Press" verknüpft wird.  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 Im folgenden Beispiel wird die Verwendung dieser Entitätsdeklaration im XML-Code als Entitätsverweis veranschaulicht.  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 Manche Parser erweitern Entitäten automatisch, wenn ein Dokument in den Speicher geladen wird. Daher werden Entitätsdeklarationen, wenn der XML-Code in den Speicher eingelesen wird, aufbewahrt und gespeichert. Wenn der Parser anschließend auf `&;`-Zeichen stößt, die einen allgemeinen Entitätsverweis kennzeichnen, sucht der Parser diesen Namen in einer Entitätsdeklarationstabelle. Der Verweis, `&publisher;`, wird durch den entsprechenden Inhalt ersetzt. Bei dem folgenden XML-Code  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 , das Erweitern des Entitätsverweises und das Ersetzen von `&publisher;` durch "Microsoft Press" führt zu folgendem erweiterten XML-Code.  
  
 **Ausgabe**  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 Es gibt viele verschiedene Entitäten. Die folgende Abbildung zeigt die einzelnen Entitätstypen und die zugehörige Terminologie.  
  
 ![Flussdiagramm für entitätstyphierarchie](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")  
  
 Die Standardeinstellung für die Microsoft .NET Framework-Implementierung des XML-Dokument Objekt Model (DOM) werden von Entitätsverweise beibehalten und die Entitäten nicht erweitert werden, wenn der XML-Code geladen wird. Die Implikation hiervon erfolgt, die wie ein Dokument in das DOM geladen wird ein **XmlEntityReference** Knoten mit die Verweisvariable `&publisher;` mit untergeordneten Knoten, die den Inhalt in der Entität darstellt, die in der DTD deklarierte, erstellt wird.  
  
 Mithilfe der `<!ENTITY publisher "Microsoft Press">` Entitätsdeklaration, das folgende Diagramm zeigt die **XmlEntity** und **XmlText** Knoten, die anhand der Entitätsdeklaration erstellt.  
  
 ![Knoten, die aus Entitätsdeklarationen erstellt](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")  
  
 Die Tatsache, ob Entitätsverweise erweitert werden oder nicht, ist entscheidend dafür, welche Knoten in der DOM-Struktur im Speicher generiert werden. Die Unterschiede zwischen den Knoten, die generiert werden, wird in den Themen erläutert [Entitätsverweise werden beibehalten](../../../../docs/standard/data/xml/entity-references-are-preserved.md) und [Entitätsverweise werden erweitert und nicht beibehalten](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
