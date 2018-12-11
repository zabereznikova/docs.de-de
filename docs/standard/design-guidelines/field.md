---
title: Feldentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: KrzysztofCwalina
ms.openlocfilehash: 34c5a163e545b78c188f37b2819962b4c7c56f80
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144350"
---
# <a name="field-design"></a>Feldentwurf
Das Prinzip der Kapselung ist eines der wichtigsten Konzepte in objektorientierten Entwurf. Dieses Prinzip besagt, dass die Daten in ein Objekt nur dieses Objekt zugegriffen werden soll.  
  
 Eine gute Möglichkeit, das Prinzip zu interpretieren ist zu sagen, dass ein Typ sollten so konzipiert sein, dass Änderungen an Feldern dieses Typs (ändert sich Name oder Typ) erfolgen können, ohne Code, außer für Elemente des Typs. Dieser Interpretation impliziert sofort, dass alle Felder privat sein müssen.  
  
 Wir schließen Konstanten und statische schreibgeschützte Felder aus dieser Einschränkung strict, da solche Felder per Definition fast nie ändern müssen.  
  
 **X DO NOT** bieten Instanzfelder, die öffentlich und/oder geschützt sind.  
  
 Für den Zugriff auf Felder anstelle von öffentlichen oder geschützten somit sollten Sie die Eigenschaften bereitstellen.  
  
 **✓ DO** verwenden Sie Konstante Felder für Konstanten, die nie geändert wird.  
  
 Der Compiler nutzt die Werte der Konstanten, Felder direkt in Aufrufen von Code. Aus diesem Grund können Konstante Werte ohne das Risiko der Unterbrechung der Kompatibilität nicht geändert werden.  
  
 **✓ DO** öffentliche statische `readonly` Felder für vordefinierte Objektinstanzen.  
  
 Wenn Sie vordefinierte Instanzen des Typs vorhanden sind, deklarieren Sie wie öffentliche schreibgeschützte statische Felder des Typs selbst.  
  
 **X DO NOT** Zuweisen von Instanzen von Typen, die auf änderbare `readonly` Felder.  
  
 Ein änderbarer Typ ist ein Typ mit Instanzen, die geändert werden kann, nachdem sie instanziiert werden. Z. B. Arrays, die meisten Auflistungen und Streams veränderlicher Typen sind jedoch <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, und <xref:System.String?displayProperty=nameWithType> sind alle unveränderlich. Die schreibgeschützten Modifizierer auf einen Typ Referenzfeld wird verhindert, dass die Instanz, die in das Feld ersetzt wird gespeichert, aber es verhindert, dass Instanzdaten des Felds nicht geändert wird, durch Aufrufen von Membern die Instanz zu ändern.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
