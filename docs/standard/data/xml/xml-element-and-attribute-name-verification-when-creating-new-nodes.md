---
title: Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
ms.openlocfilehash: 1da893261b35c6b57c4f08eb53b7701ec1d81fae
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289849"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten
Das Dokumentobjektmodell (DOM) überprüft beim Erstellen neuer Element- oder Attributknoten die Gültigkeit der Namen. Wenn die Namen ungültige Zeichen enthalten, wird eine Ausnahme ausgelöst. Wenn Sie sicherstellen möchten, dass die Namen gültig und korrekt codiert sind, müssen Sie diese mithilfe der **XmlConvert**-Klasse codieren und auf Anwendungsebene wieder decodieren. Die in **XmlWriter** enthaltenen Methoden stellen durch weitere Aktionen sicher, dass wohlgeformter XML-Code generiert wird.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
