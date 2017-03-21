---
title: Sonstige Datentypen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Object data type, data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2de377fa9dfd7ec13cdbb9b700f8485b0c0e2106
ms.lasthandoff: 03/13/2017

---
# <a name="miscellaneous-data-types-visual-basic"></a>Sonstige Datentypen (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]bietet verschiedene Datentypen, die nicht auf Zahlen oder Zeichen ausgerichtet sind. Stattdessen behandeln sie spezielle Daten wie z. B. Ja/Nein-Werte, Datum/Uhrzeit-Werte und Objekt-Adressen.  
  
 Eine Tabelle mit einer Side-by-Side-Vergleich der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Datentypen finden Sie in [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="boolean-type"></a>Boolean-Typ  
 Die [Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) ist ein Wert ohne Vorzeichen, der entweder als interpretiert wird `True` oder `False`. Die Datenbreite hängt von der implementierenden Plattform ab. Wenn eine Variable nur zwei Werten wie z. B. wahr/falsch, Ja/Nein oder ein/aus enthalten kann kann, deklarieren Sie es als `Boolean`.  
  
## <a name="date-type"></a>Date-Typ  
 Die [Date-Datentyp](../../../../visual-basic/language-reference/data-types/date-data-type.md) ist ein 64-Bit-Wert, der Datum und Uhrzeit enthält. Jedes Inkrement stellt 100 Nanosekunden verstrichene Zeit seit dem Beginn (00:00 Uhr) des 1. Januar des Jahres 1 im gregorianischen Kalender dar. Wenn eine Variable einen Datumswert und/oder eine Uhrzeitwert enthalten kann, deklarieren Sie es als `Date`.  
  
## <a name="object-type"></a>Objekttyp  
 Die [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md) ist eine 32-Bit-Adresse, die auf eine Objektinstanz innerhalb Ihrer Anwendung oder in einer anderen Anwendung verweist. Ein `Object` Variable verweisen kann, auf ein beliebiges Objekt, das die Anwendung erkennt, oder auf Daten eines beliebigen Datentyps. Dazu gehören *Werttypen*, wie z. B. `Integer`, `Boolean`, und Strukturinstanzen und *Verweistypen*, sind Instanzen von Objekten, die von Klassen erstellt haben, wie z. B. `String` und <xref:System.Windows.Forms.Form>, und array-Instanzen.</xref:System.Windows.Forms.Form>  
  
 Wenn eine Variable einen Zeiger auf eine Instanz einer Klasse speichert, die Sie zur Kompilierzeit nicht bekannt ist oder es auf Daten von verschiedenen Datentypen verweisen kann, deklarieren Sie sie als `Object`.  
  
 Der Vorteil der `Object` -Datentyp ist, Sie zum Speichern von Daten eines beliebigen Datentyps verwendet werden können. Der Nachteil besteht darin, dass zusätzliche Operationen erforderlich sind, die weitere Ausführung Zeit in Anspruch nehmen und die Anwendung verlangsamen. Wenn Sie verwenden ein `Object` fallen-Variable für Werttypen, *Boxing* und *unboxing*. Wenn Sie bei Verweistypen verwenden, fallen *spätes Binden*.  
  
## <a name="see-also"></a>Siehe auch  
 [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Numerische Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Zeichendatentypen](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
