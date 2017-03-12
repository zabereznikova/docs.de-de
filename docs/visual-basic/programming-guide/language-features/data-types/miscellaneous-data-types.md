---
title: "Miscellaneous Data Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Object data type, data types"
  - "data types [Visual Basic], choosing"
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Miscellaneous Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] bietet verschiedene Datentypen, die für andere Werte als Ziffern oder Zeichen bestimmt sind.  Mit diesen Datentypen können besondere Daten wie ja\/nein\-Werte, Datums\- bzw. Uhrzeitangaben und Objektadressen dargestellt werden.  
  
 Eine Tabelle mit einer Gegenüberstellung der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Datentypen finden Sie unter [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## Boolean\-Datentyp  
 Der [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) ist ein Wert ohne Vorzeichen, der als `True` oder `False` interpretiert wird.  Die Datenbreite hängt von der implementierenden Plattform ab.  Wenn eine Variable nur einen von zwei Werten annehmen kann, z. B. wahr\/falsch, ja\/nein, ein\/aus, deklarieren Sie sie als `Boolean`\-Variable.  
  
## Date\-Datentyp  
 Der [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) ist ein 64\-Bit\-Wert, der sowohl Datums\- als auch Uhrzeitinformationen enthält.  Dabei stellt ein Inkrement einen Zeitabschnitt von 100 Nanosekunden dar, der seit dem Beginn \(00:00 Uhr\) des 1. Januar des Jahres 1 des gregorianischen Kalenders abgelaufen ist.  Wenn eine Variable einen Datumswert, einen Uhrzeitwert oder beides enthalten kann, deklarieren Sie sie als `Date`\-Variable.  
  
## Object\-Datentyp  
 Der [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) ist eine 32\-Bit\-Adresse, die auf eine Objektinstanz in der vorliegenden Anwendung oder einer beliebigen anderen Anwendung zeigt.  Eine `Object`\-Variable kann auf jedes beliebige Objekt, das von der Anwendung erkannt wird, oder auf Daten beliebigen Typs verweisen.  Dies schließt *Werttypen*, z `Integer`, und `Boolean`Instanzen und *Verweistypen*Struktur, die Instanzen von Objekten, die von den Klassen wie `String` und <xref:System.Windows.Forms.Form>erstellt werden, und Instanzen Array ein.  
  
 Wenn eine Variable einen Zeiger auf eine Instanz einer Klasse enthält, die zur Kompilierungszeit nicht bekannt ist, oder wenn der Zeiger auf Daten unterschiedlicher Datentypen verweisen kann, deklarieren Sie die Variable als `Object`\-Variable.  
  
 Der Vorteil des `Object` Datentyps liegt darin, dass Sie ihn verwenden können, um Daten eines beliebigen Datentyps zu speichern.  Der Nachteil ist, dass zusätzliche Operationen erforderlich sind, die die Ausführungszeit verlängern und die Anwendung verlangsamen.  Wenn Sie eine `Object`\-Variable für Werttypen verwenden, kommt es zu *Boxing* und *Unboxing*.  Die Verwendung der Variablen für Verweistypen bewirkt *spätes Binden*.  
  
## Siehe auch  
 [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Character Data Types](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)