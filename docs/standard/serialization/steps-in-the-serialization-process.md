---
title: Schritte im Serialisierungsprozess
ms.date: 08/07/2017
ms.prod: .net
ms.topic: article
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cc6df422359826bc908bd412aaf89aa784be59ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="steps-in-the-serialization-process"></a>Schritte im Serialisierungsprozess
Wenn die <xref:System.Runtime.Serialization.Formatter.Serialize*>-Methode für ein [Formatierungsprogramm](xref:System.Runtime.Serialization.Formatter) aufgerufen wird, erfolgt die Objektserialisierung nach den folgenden Regeln:

- Es wird überprüft, ob das Formatierungsprogramm über einen Ersatzselektor verfügt. Ist dies beim vorliegenden Formatierungsprogramm der Fall, wird geprüft, ob der Ersatzselektor Objekte des gegebenen Typs handhaben kann. Wenn der Selektor den Objekttyp handhaben kann, wird <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType> im Ersatzselektor aufgerufen.

- Wenn kein Ersatzselektor vorhanden ist oder wenn der gegebene Ersatzselektor den Objekttyp nicht handhaben kann, wird geprüft, ob das Objekt mit dem [Serialisierbar](xref:System.SerializableAttribute)-Attribut markiert ist. Wenn dies nicht der Fall ist, wird <xref:System.Runtime.Serialization.SerializationException> ausgelöst.

- Wenn das Objekt entsprechend markiert ist, wird geprüft, ob das Objekt die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementiert. Falls dem so ist, wird die <xref:System.Runtime.Serialization.ISerializable.GetObjectData*> des Objekts aufgerufen.
  
- Wenn das Objekt <xref:System.Runtime.Serialization.ISerializable> nicht implementiert, wird nach der Standardserialisierungsrichtlinie verfahren, und alle Felder, die nicht als [Nicht serialisierbar](xref:System.NonSerializedAttribute) markiert sind, werden serialisiert.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>Siehe auch  
 [Binäre Serialisierung](binary-serialization.md)  
 [XML- und SOAP-Serialisierung](xml-and-soap-serialization.md)