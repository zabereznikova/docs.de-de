---
title: Erstellen eines kryptografischen Schemas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ef3741ef5cec720c2fb285c9aa60d610acc0be9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61909388"
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
