---
title: Auswirkungen von Namespaces auf die Entitätsverweiserweiterung für neue Knoten mit Elementen und Attributen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e2ba9964f17380e868ea5fe906a40f8b491018a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a>Auswirkungen von Namespaces auf die Entitätsverweiserweiterung für neue Knoten mit Elementen und Attributen
Da in einer Entitätsdeklaration beinahe alles enthalten sein kann, besteht die Möglichkeit, dass ein Element wie `<!ENTITY aname "<elem>test</elem>">` enthalten ist.  
  
 Wenn der XML-Code analysiert wird, wird `&aname;` zur Analysezeit nicht mit dem entsprechenden Ersetzungsinhalt erweitert. Die Erweiterung des XML-Codes wird nicht ausgeführt, da die Auflösung des Namespaces für das Element erst erfolgen kann, wenn der Knoten im Dokument platziert wurde. Bis dahin ist nicht bekannt, welcher Namespace sich im Gültigkeitsbereich befindet. Wenn der Knoten in das Dokument eingefügt wird, erfolgt die Namespaceauflösung, und der sich ergebende Entitätsinhalt wird analysiert und in die entsprechenden Knoten umgesetzt.  
  
> [!NOTE]
>  Sobald die Erweiterung für einen neu erstellten Entitätsverweisknoten erfolgt ist, wird sie nie wieder ausgeführt. Daher werden die Namespaces, die in dem Ersetzungstext für das Element verwendet werden, zum Zeitpunkt der Festlegung des übergeordneten Knotens gebunden. Sie können den Namespace jedoch für vorhandene Entitätsverweisknoten ändern, wenn Sie sie entfernen und an anderer Stelle einfügen, oder bei Entitätsverweisknoten, die mit der **CloneNode**-Methode geklont werden.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
