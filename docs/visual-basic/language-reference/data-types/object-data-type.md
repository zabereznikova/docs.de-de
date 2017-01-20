---
title: "Object Data Type | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Object"
  - "vb.Variant"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "object variables, Object type"
  - "data types [Visual Basic], assigning"
  - "Object data type"
  - "Object data type, reference"
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Object Data Type
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Speichert Adressen, die auf Objekte verweisen.  Sie können einer als `Object` deklarierten Variablen einen beliebigen Referenztyp \(Zeichenfolge, Array, Klasse oder Schnittstelle\) zuweisen.  Eine `Object`\-Variable kann darüber hinaus auf Daten eines beliebigen Werttyps \(numerisch, `Boolean`, `Char`, `Date`, Struktur oder Enumeration\) verweisen.  
  
## Hinweise  
 Der `Object`\-Datentyp kann auf Daten eines beliebigen Datentyps zeigen, einschließlich jeder Objektinstanz, die von der Anwendung erkannt wird.  Verwenden Sie `Object`, wenn Sie zur Kompilierungszeit nicht wissen, auf welchen Datentyp die Variable zeigt.  
  
 Der Standardwert von `Object` ist `Nothing` \(ein NULL\-Verweis\).  
  
## Datentypen  
 Dies bedeutet, dass Sie einer `Object`\-Variablen eine Variable, eine Konstante oder einen Ausdruck jedes beliebigen Datentyps zuweisen können.  Mithilfe der <xref:System.Type.GetTypeCode%2A>\-Methode der <xref:System.Type?displayProperty=fullName>\-Klasse können Sie den Datentyp bestimmen, auf den eine `Object`\-Variable aktuell verweist.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 Der `Object`\-Datentyp ist ein Referenztyp.  Visual Basic behandelt eine `Object`\-Variable jedoch als Werttyp, wenn sie auf Daten eines Werttyps verweist.  
  
## Speicherung  
 Unabhängig davon, auf welchen Datentyp eine `Object`\-Variable verweist, enthält sie nicht den eigentlichen Datenwert, sondern einen Zeiger auf diesen Wert.  Die `Object`\-Variable belegt vier Byte Speicherplatz, den Platz für die Speicherung der Daten, die den Wert der Variablen darstellen, ausgenommen.  Da der Code zum Lokalisieren der Daten einen Zeiger verwendet, dauert der Zugriff auf `Object`\-Variablen, die Werttypen enthalten, etwas länger als bei Variablen mit einem expliziten Typ.  
  
## Programmiertipps  
  
-   **Interop\-Überlegungen.** Wenn Sie eine Schnittstelle mit nicht für .NET Framework geschriebenen Komponenten erstellen, z. B. Automatisierungs\- oder COM\-Objekte, müssen Sie bedenken, dass die Zeigertypen anderer Umgebungen nicht mit dem `Object`\-Typ von Visual Basic kompatibel sind.  
  
-   **Leistung.** Eine Variable, die Sie mit dem `Object`\-Typ deklarieren, ist so flexibel, dass sie einen Verweis auf jedes beliebige Objekt enthalten kann.  Wenn Sie jedoch eine Methode oder eine Eigenschaft mit einer solchen Variablen aufrufen, wird immer eine *späte Bindung* \(zur Laufzeit\) ausgeführt.  Um eine *frühe Bindung* \(zur Kompilierungszeit\) und ein besseres Leistungsverhalten zu erzwingen, deklarieren Sie die Variable mit einem bestimmten Klassennamen oder wandeln sie in den betreffenden Datentyp um.  
  
     Versuchen Sie, bei der Deklaration einer Objektvariablen einen bestimmten Klassentyp, beispielsweise <xref:System.OperatingSystem>, zu verwenden – und nicht den allgemeinen `Object`\-Typ.  Verwenden Sie außerdem eine möglichst spezifische Klasse \(z. B. <xref:System.Windows.Forms.TextBox> statt <xref:System.Windows.Forms.Control>\), sodass Sie auf die zugehörigen Eigenschaften und Methoden zugreifen können.  Die verfügbaren Klassennamen können Sie in der Regel über die **Classes**\-Liste im **Objektkatalog** anzeigen.  
  
-   **Erweiterung.** Alle Datentypen und alle Referenztypen werden zum `Object`\-Datentyp erweitert.  Dies bedeutet, dass Sie jeden Typ in `Object` konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
     Wenn Sie allerdings einen Werttyp in den `Object`\-Typ umwandeln oder umgekehrt, führt Visual Basic Operationen durch, die als *Boxing* und *Unboxing* bezeichnet werden und die Ausführung verlangsamen.  
  
-   **Typzeichen.** `Object` hat kein Literaltypzeichen oder Typkennzeichen.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Object?displayProperty=fullName>\-Klasse.  
  
## Beispiel  
 Im folgenden Beispiel wird eine `Object`\-Variable, die auf eine Objektinstanz zeigt, veranschaulicht.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## Siehe auch  
 <xref:System.Object>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [How to: Determine Whether Two Objects Are Related](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [How to: Determine Whether Two Objects Are Identical](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)