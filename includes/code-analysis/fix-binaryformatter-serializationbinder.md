---
ms.openlocfilehash: 557d811e2eeaf926cb958471d214fc23c50a25f2
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590590"
---
- Verwenden Sie stattdessen ein sicheres Serialisierungsprogramm, und **lassen Sie nicht zu, dass ein Angreifer einen beliebigen zu deserialisierenden Typ angibt**. Weitere Informationen finden Sie in den [bevorzugten Alternativen](/dotnet/standard/serialization/binaryformatter-security-guide#preferred-alternatives).
- Sorgen Sie dafür, dass die serialisierten Daten manipuliert werden. Signieren Sie die serialisierten Daten nach der Serialisierung kryptografisch. Überprüfen Sie vor der Deserialisierung die kryptografische Signatur. Schützen Sie den Kryptografieschlüssel vor der Offenlegung, und entwerfen Sie Schlüssel Drehungen.
- Diese Option macht Code anfällig für Denial-of-Service-Angriffe und mögliche Angriffe auf Remote Codeausführung in der Zukunft. Weitere Informationen finden Sie im [BinaryFormatter-Sicherheitshandbuch](/dotnet/standard/serialization/binaryformatter-security-guide). Deserialisierte Typen einschränken. Implementieren Sie einen benutzerdefinierten <xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType> . Legen Sie die-Eigenschaft vor der Deserialisierung `Binder` auf eine Instanz Ihrer benutzerdefinierten <xref:System.Runtime.Serialization.SerializationBinder> in allen Codepfade fest. Lösen Sie in der überschriebenen <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> Methode, wenn der Typ unerwartet ist, eine Ausnahme aus, um die Deserialisierung zu beenden.
