---
title: Feldentwurf
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d47934c3fed17f75a97ef5da0397c6ceba53d68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571112"
---
# <a name="field-design"></a>Feldentwurf
Das Prinzip der Kapselung ist einer der wichtigsten Konzepte in eines objektorientierten Entwurfs. Dieses Prinzip gibt an, dass in einem Objekt gespeicherte Daten nur auf dieses Objekt zugegriffen werden soll.  
  
 Eine gute Möglichkeit, interpretiert das Prinzip ist zu sagen, dass ein Typ, damit Änderungen an Felder des Typs (Änderungen, Name oder Typ) vorgenommen werden können, ohne Unterbrechung Code nur für Elemente des Typs entworfen werden soll. Diese Interpretation impliziert sofort, dass alle Felder privat sein müssen.  
  
 Wir ausschließen Konstanten und statische schreibgeschützte Felder aus dieser Einschränkung strict, da Suchfelder, fast per Definition nie erforderlich sind, ändern.  
  
 **X DO NOT** bieten Instanzfelder, die öffentlich und/oder geschützt sind.  
  
 Sie sollten Eigenschaften für den Zugriff auf Felder und trifft diese öffentliche oder geschützte bereitstellen.  
  
 **✓ DO** verwenden Sie Konstante Felder für Konstanten, die nie geändert wird.  
  
 Der Compiler brennt const Felder die Werte direkt in Aufrufen von Code. Aus diesem Grund können Konstante Werte ohne beschädigen Kompatibilität nie geändert werden.  
  
 **✓ DO** öffentliche statische `readonly` Felder für vordefinierte Objektinstanzen.  
  
 Wenn die vordefinierten Instanzen des Typs vorhanden sind, deklarieren Sie diese als öffentliche schreibgeschützte statische Felder des Typs selbst.  
  
 **X DO NOT** Zuweisen von Instanzen von Typen, die auf änderbare `readonly` Felder.  
  
 Ein änderbarer Typ ist ein Typ mit Instanzen, die geändert werden können, nachdem sie instanziiert werden. Z. B. Arrays, die meisten Auflistungen und Streams änderbare Typen sind jedoch <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, und <xref:System.String?displayProperty=nameWithType> sind alle unveränderlich. Den schreibgeschützten Modifizierer auf einen Typ Verweisfeld wird verhindert, dass die Instanz, die in das Feld ersetzt wird gespeichert, aber es verhindert jedoch nicht das Feld Instanzdaten bearbeitet werden durch Aufrufen von Membern die Instanz ändern.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
