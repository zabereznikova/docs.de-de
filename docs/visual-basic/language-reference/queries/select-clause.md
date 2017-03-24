---
title: "Select Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QuerySelect"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Select statement"
  - "Select clause"
  - "queries [Visual Basic], Select"
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Select Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Definiert das Ergebnis einer Abfrage.  
  
## Syntax  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## Teile  
 `var1`  
 Optional.  Ein Alias, der verwendet werden kann, um auf die Ergebnisse des Spaltenausdrucks zu verweisen.  
  
 `fieldName1`  
 Erforderlich.  Der Name des Felds, das im Abfrageergebnis zurückgegeben werden soll.  
  
## Hinweise  
 Mit der `Select`\-Klausel können Sie die Ergebnisse definieren, die in einer Abfrage zurückgegeben werden sollen.  Dadurch können Sie die Member eines neuen anonymen Typs definieren, der von einer Abfrage erstellt wird, oder auf die Member eines benannten Typs zugreifen, der von einer Abfrage zurückgegeben wird.  Eine Abfrage muss keine `Select`\-Klausel enthalten.  Wenn Sie keine `Select`\-Klausel angeben, wird von der Abfrage ein Typ auf Grundlage aller Member der Bereichsvariablen zurückgegeben, die für den aktuellen Bereich angegeben wurden.  Weitere Informationen finden Sie unter [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  Wenn eine Abfrage einen benannten Typ erstellt, wird ein Ergebnis des Typs <xref:System.Collections.Generic.IEnumerable%601> zurückgegeben. Dabei ist `T` der erstellte Typ.  
  
 Die `Select`\-Klausel kann auf alle Variablen des aktuellen Bereichs verweisen.  Hierzu gehören die in der `From`\-Klausel \(oder den `From`\-Klauseln\) angegebenen Bereichsvariablen.  Weiterhin gehören hierzu alle neuen, in der `Aggregate`\-Klausel, der `Let`\-Klausel, der `Group By`\-Klausel oder der `Group Join`\-Klausel mit einem Alias erstellten Variablen, sowie die Variablen einer im Abfrageausdruck vorangestellten `Select`\-Klausel.  Die `Select`\-Klausel kann auch statische Werte enthalten.  Beispielsweise enthält das folgende Codebeispiel einen Abfrageausdruck, in dem die `Select`\-Klausel das Abfrageergebnis als einen neuen anonymen Typ mit den vier Membern `ProductName`, `Price`, `Discount` und `DiscountedPrice` definiert.  Die Werte für den `ProductName`\-Member und den `Price`\-Member werden aus der Bereichsvariablen product übernommen, die in der `From`\-Klausel definiert wird.  Der Wert für den `DiscountedPrice`\-Member wird in der `Let`\-Klausel berechnet.  Der `Discount`\-Member ist ein statischer Wert.  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 Die `Select`\-Klausel führt einen neuen Satz von Bereichsvariablen für nachfolgende Abfrageklauseln ein. Die vorherigen Bereichsvariablen befinden sich nicht mehr im Gültigkeitsbereich.  Die letzte `Select`\-Klausel in einem Abfrageausdruck legt den Rückgabewert der Abfrage fest.  Beispielsweise werden in der folgenden Abfrage für jede Kundenbestellung, deren Gesamtsumme größer als 500 ist, der Firmenname und die Auftrags\-ID zurückgegeben.  Die erste `Select`\-Klausel gibt die Bereichsvariablen für die `Where`\-Klausel und die zweite `Select`\-Klausel an.  Die zweite `Select`\-Klausel gibt die von der Abfrage zurückgegebenen Werte als neuen anonymen Typ an.  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 Wenn die `Select`\-Klausel ein einzelnes zurückzugebendes Element angibt, wird vom Abfrageausdruck eine Auflistung des Typs dieses einzelnen Elements zurückgegeben.  Wenn die `Select`\-Klausel mehrere zurückzugebende Elemente angibt, wird vom Abfrageausdruck eine Auflistung eines neuen anonymen Typs zurückgegeben, der auf den ausgewählten Elementen basiert.  Beispielsweise geben die beiden folgenden Abfragen auf Grundlage der `Select`\-Klausel Auflistungen von zwei verschiedenen Typen zurück.  Die erste Abfrage gibt eine Auflistung von Firmennamen als Zeichenfolgen zurück.  Die zweite Abfrage gibt eine Auflistung von `Customer`\-Objekten mit den entsprechenden Firmennamen und Adressinformationen zurück.  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## Beispiel  
 Der folgende Abfrageausdruck verwendet eine `From`\-Klausel zum Deklarieren einer Bereichsvariablen `cust` für die `customers`\-Auflistung.  Mit der `Select`\-Klausel werden der Kundenname und die ID ausgewählt und die `CompanyName`\-Spalte sowie die `CustomerID`\-Spalte der neuen Bereichsvariablen gefüllt.  Die `For Each`\-Anweisung durchläuft alle zurückgegebenen Objekte und zeigt für jeden Datensatz die `CompanyName`\-Spalte und die `CustomerID`\-Spalte an.  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)