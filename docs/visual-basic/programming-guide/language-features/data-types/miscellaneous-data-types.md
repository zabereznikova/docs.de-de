---
title: Sonstige Datentypen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 4808d87322d5b21b70ec38e2eb31b2b204938745
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821764"
---
# <a name="miscellaneous-data-types-visual-basic"></a>Sonstige Datentypen (Visual Basic)
Visual Basic bietet es sich um verschiedene Datentypen, die nicht auf die Zahlen oder Zeichen ausgerichtet sind. Stattdessen verarbeiten sie spezialisierte wie Ja/Nein-Werte, Datums-/Uhrzeitwerten und Objekt-Adressen.  
  
 Eine Tabelle mit dem ein Vergleich der Seite-an-Seite der Visual Basic-Datentypen finden Sie [Datentypen](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="boolean-type"></a>Boolean-Typ  
 Die [Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) ist ein Wert ohne Vorzeichen, der entweder als interpretiert wird `True` oder `False`. Die Datenbreite hängt von der implementierenden Plattform ab. Wenn eine Variable nur zwei-Status-Werte wie wahr/falsch, enthalten kann, Ja/Nein, oder ein/aus, deklarieren Sie sie als `Boolean`.  
  
## <a name="date-type"></a>Date-Typ  
 Die [Date-Datentyps](../../../../visual-basic/language-reference/data-types/date-data-type.md) ist ein 64-Bit-Wert, der sowohl Datums-als auch Informationen enthält. Jedes Inkrement stellt 100 Nanosekunden verstrichener Zeit seit dem Beginn (12:00 Uhr) des 1. Januar des Jahres 1 im gregorianischen Kalender dar. Wenn eine Variable einen Datumswert und/oder einem Uhrzeitwert enthalten kann, deklarieren Sie sie als `Date`.  
  
## <a name="object-type"></a>Objekttyp  
 Die [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) ist eine 32-Bit-Adresse, die auf eine Objektinstanz innerhalb Ihrer Anwendung oder in einer anderen Anwendung verweist. Ein `Object` Variable verweisen kann, um ein Objekt, das der Anwendung erkannt, oder klicken Sie auf die Daten eines beliebigen Datentyps. Dies schließt sowohl als *Werttypen*, z. B. `Integer`, `Boolean`, und Strukturinstanzen und *Verweistypen*, welche Instanzen von Objekten wie z. B. aus Klassen erstellte sind`String`und <xref:System.Windows.Forms.Form>, und die array-Instanzen.  
  
 Wenn eine Variable einen Zeiger auf eine Instanz einer Klasse gespeichert werden, die Sie zur Kompilierzeit nicht kennen, oder es auf Daten von verschiedenen Datentypen verweisen kann, deklarieren Sie sie als `Object`.  
  
 Der Vorteil der `Object` -Datentyp ist, dass Sie es, zum Speichern von Daten eines beliebigen Datentyps verwenden können. Der Nachteil ist, dass Sie zusätzliche Vorgänge anfallen, die weitere Ausführung Zeit in Anspruch nehmen, und stellen die Anwendung verlangsamen. Bei Verwendung einer `Object` Variablen für Werttypen, es fallen *Boxing* und *unboxing*. Wenn Sie es für Verweistypen verwenden, verursachen Sie *späte Bindung*.  
  
## <a name="see-also"></a>Siehe auch

- [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Numerische Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [Zeichendatentypen](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
