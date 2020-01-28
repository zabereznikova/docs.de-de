---
title: Feldentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: c00929ca499e39bd4e24d482c9413beb9cccddc1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741608"
---
# <a name="field-design"></a>Feldentwurf
Das Prinzip der Kapselung ist einer der wichtigsten Begriffe im objektorientierten Entwurf. Dieses Prinzip gibt an, dass auf Daten, die in einem Objekt gespeichert sind, nur dieses Objekt zugänglich ist.

 Eine gute Möglichkeit, das Prinzip zu interpretieren, besteht darin zu sagen, dass ein Typ so entworfen werden sollte, dass Änderungen an Feldern dieses Typs (Name oder Typänderungen) ohne einen anderen Code als für Member des Typs vorgenommen werden können. Diese Interpretation impliziert sofort, dass alle Felder privat sein müssen.

 Wir schließen Konstante und statische schreibgeschützte Felder aus dieser strikten Einschränkung aus, da solche Felder, fast definitionsgemäß, niemals geändert werden müssen.

 ❌ keine Instanzfelder bereitstellen, die öffentlich oder geschützt sind.

 Sie sollten Eigenschaften für den Zugriff auf Felder bereitstellen, anstatt sie öffentlich oder geschützt zu machen.

 ✔️ verwenden Konstante Felder für Konstanten, die sich nie ändern.

 Der Compiler verbrennt die Werte der Konstanten Felder direkt in aufrufenden Code. Daher können Konstanten Werte nie geändert werden, ohne dass die Kompatibilität unterbrochen werden muss.

 ✔️ öffentliche statische `readonly` Felder für vordefinierte Objektinstanzen verwenden.

 Wenn vordefinierte Instanzen des-Typs vorhanden sind, deklarieren Sie Sie als öffentliche schreibgeschützte statische Felder des Typs selbst.

 ❌ `readonly` Feldern keine Instanzen von änderbaren Typen zuweisen.

 Ein änderbarer Typ ist ein Typ mit-Instanzen, die geändert werden können, nachdem Sie instanziiert wurden. Arrays, die meisten Auflistungen und Streams sind z. b. änderbare Typen, <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>und <xref:System.String?displayProperty=nameWithType> sind allerdings unveränderlich. Der schreibgeschützte Modifizierer in einem Verweistyp Feld verhindert, dass die im Feld gespeicherte Instanz ersetzt wird, aber verhindert, dass die Instanzdaten des Felds durch Aufrufen von Membern, die die Instanz ändern, geändert werden.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
