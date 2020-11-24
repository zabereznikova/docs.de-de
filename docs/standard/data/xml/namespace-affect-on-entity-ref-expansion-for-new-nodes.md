---
title: Auswirkungen von Namespaces auf die Entitätsverweiserweiterung für neue Knoten mit Elementen und Attributen
ms.date: 03/30/2017
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
ms.openlocfilehash: 8ef86f05d2b39639ad5faae792eb9b2854ff0673
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830167"
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a><span data-ttu-id="643b8-102">Auswirkungen von Namespaces auf die Entitätsverweiserweiterung für neue Knoten mit Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="643b8-102">Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes</span></span>
<span data-ttu-id="643b8-103">Da in einer Entitätsdeklaration beinahe alles enthalten sein kann, besteht die Möglichkeit, dass ein Element wie `<!ENTITY aname "<elem>test</elem>">` enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="643b8-103">Because the content of an entity declaration can contain almost anything, there is a possibility that the content could contain an element like `<!ENTITY aname "<elem>test</elem>">`.</span></span>  
  
 <span data-ttu-id="643b8-104">Wenn der XML-Code analysiert wird, wird `&aname;` zur Analysezeit nicht mit dem entsprechenden Ersetzungsinhalt erweitert.</span><span class="sxs-lookup"><span data-stu-id="643b8-104">When the XML is parsed, `&aname;` is not expanded with its replacement content at parse time.</span></span> <span data-ttu-id="643b8-105">Die Erweiterung des XML-Codes wird nicht ausgeführt, da die Auflösung des Namespaces für das Element erst erfolgen kann, wenn der Knoten im Dokument platziert wurde.</span><span class="sxs-lookup"><span data-stu-id="643b8-105">The expansion of the XML is not done because resolution of the namespace for the element cannot occur until the node is placed in the document.</span></span> <span data-ttu-id="643b8-106">Bis dahin ist nicht bekannt, welcher Namespace sich im Gültigkeitsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="643b8-106">Until that time, there is no knowledge of what namespace is in scope.</span></span> <span data-ttu-id="643b8-107">Wenn der Knoten in das Dokument eingefügt wird, erfolgt die Namespaceauflösung, und der sich ergebende Entitätsinhalt wird analysiert und in die entsprechenden Knoten umgesetzt.</span><span class="sxs-lookup"><span data-stu-id="643b8-107">When the node is put into the document, then the namespace resolution occurs, and the resulting entity content is parsed into its appropriate nodes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="643b8-108">Sobald die Erweiterung für einen neu erstellten Entitätsverweisknoten erfolgt ist, wird sie nie wieder ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="643b8-108">Once the expansion occurs on a newly created entity reference node, it never reoccurs.</span></span> <span data-ttu-id="643b8-109">Daher werden die Namespaces, die in dem Ersetzungstext für das Element verwendet werden, zum Zeitpunkt der Festlegung des übergeordneten Knotens gebunden.</span><span class="sxs-lookup"><span data-stu-id="643b8-109">Therefore, the namespaces used in the replacement text for the element are bound at the time that the parent node is set.</span></span> <span data-ttu-id="643b8-110">Sie können den Namespace jedoch für vorhandene Entitätsverweisknoten ändern, wenn Sie sie entfernen und an anderer Stelle einfügen, oder bei Entitätsverweisknoten, die mit der **CloneNode**-Methode geklont werden.</span><span class="sxs-lookup"><span data-stu-id="643b8-110">However, the namespace can be changed for existing entity reference nodes when you remove and insert them somewhere else, or on entity reference nodes that are cloned with the **CloneNode** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="643b8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="643b8-111">See also</span></span>

- [<span data-ttu-id="643b8-112">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="643b8-112">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
