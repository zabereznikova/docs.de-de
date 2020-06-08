---
title: Kopieren von vorhandenen Knoten
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: 392490d04ff713529d501e199ac2496ff37de1a0
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289212"
---
# <a name="copy-existing-nodes"></a>Kopieren von vorhandenen Knoten
Ein Knoten kann mit vielen Methoden und Eigenschaften des DOM (XML Document Object Model) ausgewählt werden, z.B. mit **SelectSingleNode**, **ChildNodes[int i]** oder **Attributes[int i]** . Nachdem der Knoten ausgewählt wurde, können Sie ihn mit einer der Einfügemethoden, die für diesen speziellen Knotentyp gültig sind, in die Struktur einfügen. Die einzige Bedingung für das Einfügen eines Knotens in die Struktur besteht darin, dass das Dokument nach dem Einfügen des Knotens immer noch wohlgeformt sein muss. Wird ein vorhandener Knoten in die DOM-Struktur eingefügt, wird er aus seiner ursprünglichen Position entfernt und an der Zielposition eingefügt.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
