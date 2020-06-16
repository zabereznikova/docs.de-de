---
title: Gewährleisten der Datenintegrität über Hashcodes
description: Erfahren Sie, wie Sie die Datenintegrität mithilfe von Hashcodes in .net gewährleisten. Ein Hashwert ist ein numerischer Wert einer festen Länge, der die Daten eindeutig identifiziert.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET Framework], hash
- data integrity
- checking hash codes
- encryption [.NET Framework], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
ms.openlocfilehash: ffc5e78228f4e7c56febdc0872a0bc0fc581f162
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769053"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a>Gewährleisten der Datenintegrität über Hashcodes
Ein Hashwert ist ein numerischer Wert einer festen Länge, der die Daten eindeutig identifiziert. Hashwerte stellen große Mengen von Daten als viel kleinere numerische Werte dar, damit sie mit digitalen Signaturen verwendet werden. Sie können einen Hashwert effizienter signieren als den größeren Wert. Hashwerte sind auch zum Überprüfen der Integrität der Daten nützlich, die über unsichere Kanäle gesendet werden. Der Hashwert der empfangenen Daten kann mit dem Hashwert der Daten verglichen werden, da sie gesendet wurden, um festzustellen, ob die Daten verändert wurden.  
  
 In diesem Thema wird beschrieben, wie Hashcodes mit den Klassen im <xref:System.Security.Cryptography?displayProperty=nameWithType>-Namespace generiert und überprüft werden.  
  
## <a name="generating-a-hash"></a>Generieren eines Hashs  
 Die verwalteten Hashklassen können entweder ein Bytearray oder ein verwaltetes Streamobjekt hashen. Im folgenden Beispiel wird der SHA1-Hashalgorithmus verwendet, um einen Hashwert für eine Zeichenfolge zu erstellen. Im Beispiel wird die <xref:System.Text.UnicodeEncoding>-Klasse verwendet, um die Zeichenfolge in ein Bytearray zu konvertieren, dem mithilfe der <xref:System.Security.Cryptography.SHA1Managed>-Klasse ein Hash hinzugefügt werden soll. Der Hashwert wird dann in der Konsole angezeigt.  

 Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256 oder höher.
  
 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 Dieser Code zeigt die folgende Zeichenfolge in der Konsole an:  
  
 `59 4 248 102 77 97 142 201 210 12 224 93 25 41 100 197 213 134 130 135`  
  
## <a name="verifying-a-hash"></a>Überprüfen eines Hashs  
 Die Daten können mit einem Hashwert verglichen werden, um die Integrität zu bestimmen. In der Regel werden die Daten zu einem bestimmten Zeitpunkt gehasht, und der Hashwert wird entsprechend geschützt. Zu einem späteren Zeitpunkt werden die Daten erneut gehasht und mit dem geschützten Wert verglichen. Wenn die Hashwerte übereinstimmen, wurden die Daten nicht geändert. Wenn die Werte nicht übereinstimmen, sind die Daten beschädigt wurden. Damit dieses System funktioniert, muss der geschützte Hash verschlüsselt oder vor allen nicht vertrauenswürdigen Parteien geheim gehalten werden.  
  
 Im folgenden Beispiel wird der vorherige Hashwert einer Zeichenfolge mit einem neuen Hashwert verglichen. In diesem Beispiel wird jedes Byte der Hashwerte durchlaufen und verglichen.  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 Wenn die beiden Hashwerte übereinstimmen, zeigt dieser Code Folgendes in der Konsole an:  
  
```console  
The hash codes match.  
```  
  
 Wenn sie nicht übereinstimmen, zeigt der Code Folgendes an:  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Kryptografiedienste](cryptographic-services.md)
