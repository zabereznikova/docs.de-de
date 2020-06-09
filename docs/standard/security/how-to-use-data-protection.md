---
title: 'Vorgehensweise: Verwenden des Datenschutzes'
description: Erfahren Sie, wie Sie Datenschutz durchzugreifen auf die Datenschutz-API (Data Protection API, DPAPI) in .NET verwenden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: c7f88105727dfd33c87a815054aa317ac2052e83
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598592"
---
# <a name="how-to-use-data-protection"></a>Vorgehensweise: Verwenden des Datenschutzes
.NET Framework bietet Zugriff auf die Datenschutz-API, die es Ihnen ermöglicht, Daten mithilfe von Informationen vom aktuellen Benutzerkonto oder Computer zu verschlüsseln.  Wenn Sie die Datenschutz-API verwenden, umgehen Sie die schwierige Aufgabe, einen kryptografischen Schlüssel explizit zu generieren und zu speichern.  
  
 Verwenden Sie die <xref:System.Security.Cryptography.ProtectedMemory>-Klasse, um ein Array aus In-Memory-Bytes zu verschlüsseln.  Diese Funktionalität ist ab Microsoft Windows XP verfügbar.  Sie können angeben, dass der durch den aktuellen Prozess verschlüsselte Speicher nur durch den aktuellen Prozess, durch alle Prozesse oder von demselben Benutzerkontext entschlüsselt werden kann.  In der <xref:System.Security.Cryptography.MemoryProtectionScope>-Enumeration finden Sie eine ausführliche Beschreibung der <xref:System.Security.Cryptography.ProtectedMemory>-Optionen.  
  
 Verwenden Sie die <xref:System.Security.Cryptography.ProtectedData>-Klasse, um eine Kopie eines Bytearrays zu verschlüsseln. Diese Funktionalität ist ab Microsoft Windows 2000 verfügbar.  Sie können angeben, dass Daten, die über das aktuelle Benutzerkonto verschlüsselt wurden, nur über dasselbe Benutzerkonto oder über jedes Konto auf dem Computer entschlüsselt werden können.  In der <xref:System.Security.Cryptography.DataProtectionScope>-Enumeration finden Sie eine ausführliche Beschreibung der <xref:System.Security.Cryptography.ProtectedData>-Optionen.  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a>So verschlüsseln Sie im Arbeitsspeicher befindliche Daten mithilfe von Datenschutz  
  
1. Rufen Sie die statische <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A>-Methode auf, wobei Sie ein Array zu verschlüsselnder Bytes, die Entropie und den Speicherschutzbereich übergeben.  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a>So entschlüsseln Sie im Arbeitsspeicher befindliche Daten mithilfe von Datenschutz  
  
1. Rufen Sie die statische <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A>-Methode auf, wobei Sie ein Array zu entschlüsselnder Bytes und den Speicherschutzbereich übergeben.  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a>So verschlüsseln Sie Daten in eine Datei oder einen Stream mithilfe von Datenschutz  
  
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
  
- Fügen Sie einen Verweis auf `System.Security.dll` ein.  
  
- Fügen Sie die Namespaces <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> und <xref:System.Text> ein.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
