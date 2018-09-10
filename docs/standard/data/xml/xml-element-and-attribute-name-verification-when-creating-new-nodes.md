---
title: Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 008cf14e63b8458feebf26eaf27be516bb79f933
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216040"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten
Das Dokumentobjektmodell (DOM) überprüft beim Erstellen neuer Element- oder Attributknoten die Gültigkeit der Namen. Wenn die Namen ungültige Zeichen enthalten, wird eine Ausnahme ausgelöst. Wenn Sie sicherstellen möchten, dass die Namen gültig und korrekt codiert sind, müssen Sie diese mithilfe der **XmlConvert**-Klasse codieren und auf Anwendungsebene wieder decodieren. Die in **XmlWriter** enthaltenen Methoden stellen durch weitere Aktionen sicher, dass wohlgeformter XML-Code generiert wird.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
