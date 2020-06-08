---
title: Entitätsverweise werden erweitert und nicht beibehalten
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: ffd97806-ab43-4538-8de2-5828bfbbde57
ms.openlocfilehash: 1d26e9a35497bb0d5293e8a5b630bf4356325401
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292045"
---
# <a name="entity-references-are-expanded-and-not-preserved"></a>Entitätsverweise werden erweitert und nicht beibehalten
Wenn der Entitätsverweis erweitert und durch den Text ersetzt wird, für den er steht, wird der **XmlEntityReference**-Knoten nicht erstellt. Stattdessen wird die Entitätsdeklaration analysiert, und die Knoten, die aus dem Inhalt der Deklaration erstellt werden, werden an die Stelle von **XmlEntityReference** kopiert. Daher wird im `&publisher;`-Beispiel `&publisher;` nicht gespeichert. Stattdessen wird ein **XmlText**-Knoten erstellt.  
  
 ![Erweiterte Struktur](media/xmlentityref-expanded-nodes.gif "xmlentityref_expanded_nodes")  
Struktur für Entitätsverweise, die erweitert werden  
  
 Zeichenentitäten, z. B. `B` oder `<`, werden nicht beibehalten. Stattdessen werden sie stets erweitert und als Textknoten dargestellt.  
  
 Damit **XmlEntityReference**-Knoten und die untergeordneten Knoten des damit verknüpften Entitätsverweises beibehalten werden, legen Sie das **EntityHandling**-Flag auf **ExpandCharEntities** fest. Andernfalls behalten Sie den Standardwert des **EntityHandling**-Flags (**ExpandEntities**) bei. In diesem Fall werden im DOM keine Entitätsverweisknoten angezeigt. Die Knoten werden durch die Knoten ersetzt, die Kopien der untergeordneten Knoten der Entitätsdeklaration sind.  
  
 Wenn Entitätsverweise nicht beibehalten werden, hat dies u. U. den Nebeneffekt, dass der Zielanwendung beim Speichern und Übergeben des Dokuments an eine andere Anwendung nicht bekannt ist, dass die Knoten durch einen Entitätsverweis erstellt wurden. Wenn die Entitätsverweise dagegen beibehalten werden, erkennt die Zielanwendung den Entitätsverweis und liest die untergeordneten Knoten. Es ist offensichtlich, dass die untergeordneten Knoten die Informationen darstellen, die sich in der Entitätsdeklaration befanden. Wenn Entitätsverweise beibehalten werden, hat das DOM theoretisch die folgende Struktur:  
  
 XmlElement: Verleger  
  
 XmlEntityReference: `&publisher;`  
  
 XmlText: Microsoft Press  
  
 Wenn Entitätsverweise im DOM erweitert werden (dies ist die Standardvorgehensweise), ergibt sich folgende Struktur:  
  
 XmlElement: Verleger  
  
 XmlText: Microsoft Press  
  
 Beachten Sie, dass der Entitätsverweisknoten nun nicht mehr vorhanden ist, und die Zielanwendung nicht erkennen kann, dass der **XmlText**-Knoten mit „Microsoft Press“ aus einer Entitätsdeklaration erstellt wurde.  
  
 Wenn Sie einen Reader verwenden, der keine Entitäten auflösen kann, löst die **Load**-Methode beim Auffinden eines Entitätsverweises eine Ausnahme aus.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
