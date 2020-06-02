---
title: Erstellen eines kryptografischen Schemas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
ms.openlocfilehash: 1478873c1c2dc73ca31c9078e39a3902966bf674
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288419"
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

- [Kryptografiedienste](cryptographic-services.md)
