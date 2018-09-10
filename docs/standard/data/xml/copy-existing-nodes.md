---
title: Kopieren von vorhandenen Knoten
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eda5c9b4851b29c0a76e45414d7c47ba52252455
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252869"
---
# <a name="copy-existing-nodes"></a>Kopieren von vorhandenen Knoten
Ein Knoten kann mit vielen Methoden und Eigenschaften des DOM (XML Document Object Model) ausgewählt werden, z.B. mit **SelectSingleNode**, **ChildNodes[int i]** oder **Attributes[int i]**. Nachdem der Knoten ausgewählt wurde, können Sie ihn mit einer der Einfügemethoden, die für diesen speziellen Knotentyp gültig sind, in die Struktur einfügen. Die einzige Bedingung für das Einfügen eines Knotens in die Struktur besteht darin, dass das Dokument nach dem Einfügen des Knotens immer noch wohlgeformt sein muss. Wird ein vorhandener Knoten in die DOM-Struktur eingefügt, wird er aus seiner ursprünglichen Position entfernt und an der Zielposition eingefügt.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
