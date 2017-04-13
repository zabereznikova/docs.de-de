---
title: "Gewusst wie: Auff&#252;llen einer Zahl mit f&#252;hrenden Nullen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Formatieren [.NET Framework], Zahlen"
  - "Zahlenformatierung [.NET Framework]"
  - "Zahlen [.NET Framework], Formatzeichenfolgen"
  - "Numerische Formatzeichenfolgen [.NET Framework]"
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Auff&#252;llen einer Zahl mit f&#252;hrenden Nullen
Führende Nullen können Sie mithilfe der [numerischen Standardformatzeichenfolge](../../../docs/standard/base-types/standard-numeric-format-strings.md) "D" zusammen mit einem Genauigkeitsbezeichner zu einer Ganzzahl hinzufügen.  Zu Ganz\- und Gleitkommazahlen können Sie führende Nullen mithilfe einer [benutzerdefinierten numerischen Formatzeichenfolge](../../../docs/standard/base-types/custom-numeric-format-strings.md) hinzufügen.  In diesem Thema lernen Sie beide Methoden zum Auffüllen einer Zahl mit führenden Nullen kennen.  
  
### Ganzzahl bis zu einer bestimmten Länge mit führenden Nullen auffüllen  
  
1.  Bestimmen Sie die Mindestanzahl an Ziffern, die der Ganzzahlwert anzeigen soll.  Schließen Sie alle führenden Ziffern in diese Zahl ein.  
  
2.  Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.  
  
    -   Um sie als Dezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`\-Methode auf und übergeben Sie die Zeichenfolge "D*n*" als Wert des `format`\-Parameters, wobei *n* die minimale Länge der Zeichenfolge darstellt.  
  
    -   Um sie als Hexadezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`\-Methode auf und übergeben Sie die Zeichenfolge "X*n*" als Wert des `format`\-Parameters, wobei *n* die minimale Länge der Zeichenfolge darstellt.  
  
     Sie können die Formatzeichenfolge auch in einer Methode wie z. B. <xref:System.String.Format%2A> oder <xref:System.Console.WriteLine%2A> verwenden, die [kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md) unterstützt.  
  
 Im folgenden Beispiel sind mehrere Ganzzahlwerte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Zeichen beträgt.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### Ganzzahl mit einer bestimmten Anzahl führender Nullen auffüllen  
  
1.  Bestimmen Sie, wie viele führende Nullen der Ganzzahlwert anzeigen soll.  
  
2.  Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.  Zum Formatieren der Ganzzahl als Dezimalwert benötigen Sie den Standardformatbezeichner "D", für einen Hexadezimalwert benötigen Sie den Standardformatbezeichner "X".  
  
3.  Bestimmen Sie die Länge der noch nicht mit Nullen aufgefüllten numerischen Zeichenfolge, indem Sie die `ToString("D").Length`\- oder die `ToString("X").Length`\-Methode des Ganzzahlwerts aufrufen.  
  
4.  Fügen Sie die Anzahl der führenden Nullen, die in die formatierte Zeichenfolge eingefügt werden sollen, zur Länge der nicht aufgefüllten numerischen Zeichenfolge hinzu.  Dies ergibt die Gesamtlänge der mit Nullen aufgefüllten Zeichenfolge.  
  
5.  Rufen Sie die `ToString(String)`\-Methode des Ganzzahlwerts auf und übergeben Sie die Zeichenfolge "D*n*" für Dezimalzeichenfolgen und "X*n*" für Hexadezimalzeichenfolgen, wobei *n* die Gesamtlänge der mit Nullen aufgefüllten Zeichenfolge darstellt.  Sie können die Formatzeichenfolge "D*n*" oder "X*n*" auch in Methoden verwenden, die kombinierte Formatierung unterstützen.  
  
 Im folgenden Beispiel wird ein Ganzzahlwert mit fünf führenden Nullen aufgefüllt.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### Numerischen Wert bis zu einer bestimmten Länge mit führenden Nullen auffüllen  
  
1.  Bestimmen Sie, über wie viele Ziffern links des Dezimaltrennzeichens die Zeichenfolgendarstellung der Zahl verfügen soll.  Schließen Sie alle führenden Nullen in diese Gesamtzahl der Ziffern ein.  
  
2.  Definieren Sie eine benutzerdefinierte numerische Formatzeichenfolge, in der die Mindestanzahl an Nullen mit dem Null\-Platzhalter \("0"\) dargestellt wird.  
  
3.  Rufen Sie die `ToString(String)`\-Methode der Zahl auf und übergeben sie die benutzerdefinierte Formatzeichenfolge.  Sie können die benutzerdefinierte Formatzeichenfolge auch mit Methoden verwenden, die kombinierte Formatierung unterstützen.  
  
 Im folgenden Beispiel sind mehrere numerische Werte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Ziffern links des Dezimaltrennzeichens beträgt.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### Numerischen Wert mit einer bestimmten Anzahl führender Nullen auffüllen  
  
1.  Bestimmen Sie, über wie viele führende Nullen der numerische Wert verfügen soll.  
  
2.  Bestimmen Sie die Anzahl der Ziffern links des Dezimaltrennzeichens in der nicht aufgefüllten numerischen Zeichenfolge.  Gehen Sie dazu wie folgt vor:  
  
    1.  Bestimmen Sie, ob die Zeichenfolgendarstellung der Zahl ein Symbol für das Dezimaltrennzeichen beinhaltet.  
  
    2.  Wenn sie ein Dezimaltrennzeichen enthält, bestimmen Sie die Anzahl der Zeichen links des Dezimaltrennzeichens.  
  
         \- oder \-  
  
         Wenn sie kein Dezimaltrennzeichen enthält, bestimmen Sie die Länge der Zeichenfolge.  
  
3.  Erstellen Sie eine benutzerdefinierte Formatzeichenfolge, in der die gewünschte Anzahl führender Nullen in der Zeichenfolge mit dem Null\-Platzhalter \("0"\) und die Ziffern in der Standardzeichenfolge mit dem Null\-Platzhalter \("0"\) oder dem Ziffernplatzhalter \("\#"\) angegeben werden.  
  
4.  Übergeben Sie die benutzerdefinierte Formatzeichenfolge als Parameter an die `ToString(String)`\-Methode der Zahl oder an eine Methode, die kombinierte Formatierung unterstützt.  
  
 Im folgenden Beispiel werden zwei <xref:System.Double>\-Werte mit fünf führenden Nullen aufgefüllt.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## Siehe auch  
 [Benutzerdefinierte Zahlenformatzeichenfolgen](../../../docs/standard/base-types/custom-numeric-format-strings.md)   
 [Standardmäßige Zahlenformatzeichenfolgen](../../../docs/standard/base-types/standard-numeric-format-strings.md)   
 [Kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md)