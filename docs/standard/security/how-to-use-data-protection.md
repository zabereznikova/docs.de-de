---
title: 'Vorgehensweise: Verwenden des Datenschutzes'
description: Erfahren Sie, wie Sie Datenschutz durchzugreifen auf die Datenschutz-API (Data Protection API, DPAPI) in .NET verwenden.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET], data protection API
- data [.NET], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET], data protection API
- data protection API [.NET]
- decryption
- data [.NET], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: d3fe7ef3ddbc6e75a248101829b11a8abcb3c15a
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282054"
---
# <a name="how-to-use-data-protection"></a>Vorgehensweise: Verwenden des Datenschutzes

> [!NOTE]
> Dieser Artikel bezieht sich auf Windows.
>
> Weitere Informationen zu ASP.net Core finden Sie unter [ASP.net Core Datenschutz](/aspnet/core/security/data-protection/introduction).

.Net bietet Zugriff auf die Datenschutz-API (Data Protection API, DPAPI), mit der Sie Daten mithilfe von Informationen aus dem aktuellen Benutzerkonto oder-Computer verschlüsseln können.  Wenn Sie die Datenschutz-API verwenden, umgehen Sie die schwierige Aufgabe, einen kryptografischen Schlüssel explizit zu generieren und zu speichern.  
  
Verwenden Sie die <xref:System.Security.Cryptography.ProtectedData>-Klasse, um eine Kopie eines Bytearrays zu verschlüsseln. Diese Funktionalität ist in .NET Framework, .net Core und .net 5 verfügbar.  Sie können angeben, dass Daten, die über das aktuelle Benutzerkonto verschlüsselt wurden, nur über dasselbe Benutzerkonto oder über jedes Konto auf dem Computer entschlüsselt werden können.  In der <xref:System.Security.Cryptography.DataProtectionScope>-Enumeration finden Sie eine ausführliche Beschreibung der <xref:System.Security.Cryptography.ProtectedData>-Optionen.  
  
## <a name="encrypt-data-to-a-file-or-stream-using-data-protection"></a>Verschlüsseln von Daten in einer Datei oder einem Stream mithilfe von Datenschutz  
  
1. Erstellen Sie eine zufällige Entropie.  
  
2. Rufen Sie die statische <xref:System.Security.Cryptography.ProtectedData.Protect%2A>-Methode auf, wobei Sie ein Array zu verschlüsselnder Bytes, die Entropie und den Datenschutzbereich übergeben.  
  
3. Schreiben Sie die verschlüsselten Daten in eine Datei oder einen Stream.  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a>So entschlüsseln Sie Daten aus einer Datei oder einem Stream mithilfe von Datenschutz  
  
1. Lesen Sie die verschlüsselten Daten aus einer Datei oder einem Stream.  
  
2. Rufen Sie die statische <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A>-Methode auf, wobei Sie ein Array zu entschlüsselnder Bytes und den Datenschutzbereich übergeben.  
  
## <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden zwei Arten von Verschlüsselung und Entschlüsselung veranschaulicht.  Im Codebeispiel wird zunächst ein im Arbeitsspeicher befindliches Array aus Bytes verschlüsselt und anschließend entschlüsselt.  Danach wird eine Kopie eines Bytearrays verschlüsselt, wird diese Kopie in einer Datei gespeichert, werden die Daten aus der Datei zurückgeladen und werden die Daten entschlüsselt.  Im Beispiel werden die ursprünglichen Daten, die verschlüsselten Daten und die entschlüsselten Daten angezeigt.

[!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
[!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

Dieses Beispiel wird nur kompiliert und ausgeführt, wenn .NET Framework und unter Windows ausgeführt wird.

- Fügen Sie einen Verweis auf `System.Security.dll` ein.  
  
- Fügen Sie die Namespaces <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> und <xref:System.Text> ein.  
  
## <a name="see-also"></a>Weitere Informationen

- [Kryptografiemodell](cryptography-model.md)
- [Kryptografische Dienste](cryptographic-services.md)
- [Plattformübergreifende Kryptografie](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
- [ASP.net Core Datenschutz](/aspnet/core/security/data-protection/introduction)
