---
title: Feldentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: 3a5ae985ab161899fbb5e96f9b0ef0cfa90b957c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289745"
---
# <a name="field-design"></a>Feldentwurf
Das Prinzip der Kapselung ist einer der wichtigsten Begriffe im objektorientierten Entwurf. Dieses Prinzip gibt an, dass auf Daten, die in einem Objekt gespeichert sind, nur dieses Objekt zugänglich ist.

 Eine gute Möglichkeit, das Prinzip zu interpretieren, besteht darin zu sagen, dass ein Typ so entworfen werden sollte, dass Änderungen an Feldern dieses Typs (Name oder Typänderungen) ohne einen anderen Code als für Member des Typs vorgenommen werden können. Diese Interpretation impliziert sofort, dass alle Felder privat sein müssen.

 Wir schließen Konstante und statische schreibgeschützte Felder aus dieser strikten Einschränkung aus, da solche Felder, fast definitionsgemäß, niemals geändert werden müssen.

 ❌Stellen Sie keine Instanzfelder bereit, die öffentlich oder geschützt sind.

 Sie sollten Eigenschaften für den Zugriff auf Felder bereitstellen, anstatt sie öffentlich oder geschützt zu machen.

 ✔️ verwenden Konstante Felder für Konstanten, die sich nie ändern.

 Der Compiler verbrennt die Werte der Konstanten Felder direkt in aufrufenden Code. Daher können Konstanten Werte nie geändert werden, ohne dass die Kompatibilität unterbrochen werden muss.

 ✔️ öffentliche statische `readonly` Felder für vordefinierte Objektinstanzen verwenden.

 Wenn vordefinierte Instanzen des-Typs vorhanden sind, deklarieren Sie Sie als öffentliche schreibgeschützte statische Felder des Typs selbst.

 ❌Weisen Sie Feldern keine Instanzen von änderbaren Typen zu `readonly` .

 Ein änderbarer Typ ist ein Typ mit-Instanzen, die geändert werden können, nachdem Sie instanziiert wurden. Arrays, die meisten Auflistungen und Streams sind z. b. änderbare Typen, aber <xref:System.Int32?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType> und <xref:System.String?displayProperty=nameWithType> sind unveränderlich. Der schreibgeschützte Modifizierer in einem Verweistyp Feld verhindert, dass die im Feld gespeicherte Instanz ersetzt wird, aber verhindert, dass die Instanzdaten des Felds durch Aufrufen von Membern, die die Instanz ändern, geändert werden.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfs Richtlinien für Member](member.md)
- [Framework-Entwurfs Richtlinien](index.md)
