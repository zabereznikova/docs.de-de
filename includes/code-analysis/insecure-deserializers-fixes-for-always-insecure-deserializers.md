---
author: dotpaul
ms.author: paulming
ms.date: 05/01/2019
ms.topic: include
ms.openlocfilehash: cf944ae9ca200d34a1f0f32e68bf3aee73a9500a
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590593"
---
- Verwenden Sie, wenn möglich, stattdessen ein sicheres Serialisierungsprogramm, und **lassen Sie nicht zu, dass ein Angreifer einen beliebigen zu deserialisierenden Typ angibt**. Zu den sichereren serialisierungssoren zählen:

  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -Nie verwenden <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType> . Wenn Sie einen Typresolver verwenden müssen, beschränken Sie deserialisierte Typen auf eine erwartete Liste.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft JSON.net: Verwenden Sie typamehandult. None. Wenn Sie einen anderen Wert für typamehanding verwenden müssen, beschränken Sie deserialisierte Typen auf eine erwartete Liste mit einem benutzerdefinierten iserializationbinder.
  - Protokollpuffer

- Sorgen Sie dafür, dass die serialisierten Daten manipuliert werden. Signieren Sie die serialisierten Daten nach der Serialisierung kryptografisch. Überprüfen Sie vor der Deserialisierung die kryptografische Signatur. Schützen Sie den Kryptografieschlüssel vor der Offenlegung, und entwerfen Sie Schlüssel Drehungen.
