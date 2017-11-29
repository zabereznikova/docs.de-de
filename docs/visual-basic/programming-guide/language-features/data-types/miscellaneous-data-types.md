---
title: Sonstige Datentypen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6bb86bb6d203aa4e6bdded27a4cb78a8155ddec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="miscellaneous-data-types-visual-basic"></a>Sonstige Datentypen (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]stellt mehrere Datentypen, die nicht auf Zahlen oder Zeichen ausgerichtet sind. Stattdessen verarbeiten sie spezielle Daten wie z. B. Ja/Nein-Werte, Datums-/Uhrzeitwerte und Objekt-Adressen.  
  
 Für eine Tabelle mit einer Seite-an-Seite-Vergleich, der die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Datentypen finden Sie unter [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="boolean-type"></a>Boolean-Typ  
 Die [booleschen Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) ist ein Wert ohne Vorzeichen, die entweder als interpretiert wird `True` oder `False`. Die Breite hängt von der implementierenden Plattform ab. Wenn eine Variable Ja/Nein, oder ein/aus nur zwei Status Werte wie wahr/falsch, enthalten kann, deklarieren Sie es als `Boolean`.  
  
## <a name="date-type"></a>Date-Typ  
 Die [Datumsdatentyp](../../../../visual-basic/language-reference/data-types/date-data-type.md) ist ein 64-Bit-Wert, der Datums-und Uhrzeitinformationen enthält. Jedes Inkrement stellt 100 Nanosekunden verstrichener Zeit seit dem Beginn (00:00 Uhr) des 1. Januar des Jahres 1 im gregorianischen Kalender dar. Wenn eine Variable einen Datumswert und/oder einen Time-Wert enthalten kann, deklarieren Sie es als `Date`.  
  
## <a name="object-type"></a>Objekttyp  
 Die [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md) ist eine 32-Bit-Adresse, die auf eine Objektinstanz innerhalb der Anwendung oder in einer anderen Anwendung verweist. Ein `Object` Variable verweisen kann, auf ein beliebiges Objekt, das die Anwendung erkennt, oder klicken Sie auf Daten eines beliebigen Datentyps. Dies schließt sowohl *Werttypen*, wie z. B. `Integer`, `Boolean`, und Strukturinstanzen und *Referenztypen*, wobei es sich um Instanzen von Objekten, z. B. von Klassen erstellt `String`und <xref:System.Windows.Forms.Form>, und die array-Instanzen.  
  
 Wenn eine Variable ein Zeiger auf eine Instanz einer Klasse gespeichert, die Sie zur Kompilierzeit nicht kennen oder es auf Daten von verschiedenen Datentypen verweisen kann, deklarieren Sie es als `Object`.  
  
 Der Vorteil der `Object` -Datentyp ist, dass Sie zum Speichern von Daten eines beliebigen Datentyps verwendet werden können. Der Nachteil ist, dass Sie zusätzliche Vorgänge verursacht, die weitere Ausführung Zeit in Anspruch nehmen, und stellen Ihre Anwendung langsamer ausgeführt. Bei Verwendung einer `Object` Variable für Werttypen anfallen *Boxing* und *unboxing*. Wenn Sie es für Verweistypen verwenden, verursachen *spätes Binden*.  
  
## <a name="see-also"></a>Siehe auch  
 [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Numerische Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [Zeichendatentypen](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
