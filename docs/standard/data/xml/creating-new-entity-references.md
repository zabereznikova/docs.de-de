---
title: Erstellen von neuen Entitätsverweisen
ms.date: 03/30/2017
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
ms.openlocfilehash: 5d1411b38ee79705cad3375aea1b95265c1ab61a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829322"
---
# <a name="creating-new-entity-references"></a>Erstellen von neuen Entitätsverweisen
Mit der **CreateEntityReference**-Methode wird ein neuer **XmlEntityReference**-Knoten erstellt. Das Dokumentobjektmodell (DOM) überprüft, ob der Entitätsname, auf den verwiesen wird, bereits deklariert ist. Wenn dies der Fall ist, wird eine Kopie der untergeordneten Knoten des **XmlEntityReference**-Knotens aus dem Entitätsdeklarationsknoten erstellt. Wenn keine übereinstimmende Entitätsdeklaration vorhanden ist, wird eine leerer Textknoten als einziger untergeordneter Knoten des Entitätsdeklarationsknotens angefügt. Da es sich bei den untergeordneten Knoten des **XmlEntityReference**-Knotens um Kopien anderer Knoten handelt, sind diese Knoten schreibgeschützt und können nicht geändert werden.  
  
 Wenn die Knoten kopiert werden, kann ein Namespace im Gültigkeitsbereich an der Position des Entitätsverweises vorhanden sein. Dieser Namespace wirkt sich auf die Konfiguration der generierten Element- oder Attributknoten aus.  
  
> [!NOTE]
> Das DOM fügt **EntityReference** nur dann untergeordnete Knoten hinzu, wenn Sie den **EntityReference**-Knoten in das Dokument einfügen. Neu erstellte **EntityReference**-Knoten weisen keine untergeordneten Knoten auf.  
  
 Obwohl es sich bei **XmlDataDocument** um eine von **XmlDocument** abgeleitete Klasse handelt, wird das Erstellen von Entitätsverweisen von **XmlDataDocument** nicht unterstützt. Dies liegt daran, dass untergeordnete Elemente von **EntityReference** schreibgeschützt sind. Die untergeordneten Knoten eines **EntityReference**-Knotens können mehr als eine Region umfassen. In diesem Fall ist der Teil einer Zeile schreibgeschützt, der mit der Region mit einem Teil einer **EntityReference** verknüpft ist.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
