---
title: Erstellen eines kryptografischen Schemas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
ms.openlocfilehash: 00fff5f346633a9682d75cf6a3be7e8e7d5db7e8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706291"
---
# <a name="creating-a-cryptographic-scheme"></a>Erstellen eines kryptografischen Schemas
Die kryptografischen Komponenten von .NET Framework können kombiniert werden, um unterschiedliche Schemas zum Ver- und Entschlüsseln von Daten zu erstellen.  
  
 Für ein einfaches kryptografisches Schema zum Ver- und Entschlüsseln von Daten können die folgenden Schritte angegeben sein:  
  
1. Jeder Teilnehmer generiert ein Paar aus privatem und öffentlichem Schlüssel.  
  
2. Die Teilnehmer tauschen ihre öffentlichen Schlüssel aus.  
  
3. Jeder Teilnehmer generiert einen geheimen Schlüssel, z. B. für die TripleDES-Verschlüsselung, und verschlüsselt den neu erstellen Schlüssel mit dem öffentlichen Schlüssel des anderen Teilnehmers.  
  
4. Jeder Teilnehmer sendet die Daten an den jeweils anderen Teilnehmer und kombiniert den geheimen Schlüssel des anderen in einer bestimmten Folge mit dem eigenen Schlüssel, um einen neuen geheimen Schlüssel zu erstellen.  
  
5. Danach beginnen die Teilnehmer eine Konversation mit symmetrischer Verschlüsselung.  
  
 Das Erstellen eines kryptografischen Schemas ist keine leichte Aufgabe.
  
## <a name="see-also"></a>Siehe auch

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
