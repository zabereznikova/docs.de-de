---
title: 'Gewusst wie: Auffüllen einer Zahl mit führenden Nullen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ce3b59db027ffebf616a035b018629cb7aed30c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569771"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a>Gewusst wie: Auffüllen einer Zahl mit führenden Nullen
Führende Nullen können Sie mithilfe der [numerischen Standardformatzeichenfolge](../../../docs/standard/base-types/standard-numeric-format-strings.md) „D“ zusammen mit einem Genauigkeitsbezeichner zu einer Ganzzahl hinzufügen. Ganz- und Gleitkommazahlen können Sie führende Nullen mithilfe einer [benutzerdefinierten numerischen Formatzeichenfolge](../../../docs/standard/base-types/custom-numeric-format-strings.md) hinzufügen. In diesem Thema lernen Sie beide Methoden zum Auffüllen einer Zahl mit führenden Nullen kennen.  
  
### <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a>Ganzzahl bis zu einer bestimmten Länge mit führenden Nullen auffüllen  
  
1.  Bestimmen Sie die Mindestanzahl an Ziffern, die der Ganzzahlwert anzeigen soll. Schließen Sie alle führenden Ziffern in diese Zahl ein.  
  
2.  Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.  
  
    -   Um sie als Dezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge "D*n*" als Wert des `format`-Parameters, wobei *n* die minimale Länge der Zeichenfolge darstellt.  
  
    -   Um sie als Hexadezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge "X*n*" als Wert des `format`-Parameters, wobei *n* die minimale Länge der Zeichenfolge darstellt.  
  
     Sie können die Formatzeichenfolge auch in einer Methode wie <xref:System.String.Format%2A> oder <xref:System.Console.WriteLine%2A> verwenden, die die [kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md) unterstützt.  
  
 Im folgenden Beispiel sind mehrere Ganzzahlwerte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Zeichen beträgt.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a>Ganzzahl mit einer bestimmten Anzahl führender Nullen auffüllen  
  
1.  Bestimmen Sie, wie viele führende Nullen der Ganzzahlwert anzeigen soll.  
  
2.  Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll. Zum Formatieren der Ganzzahl als Dezimalwert benötigen Sie den Standardformatbezeichner "D", für einen Hexadezimalwert benötigen Sie den Standardformatbezeichner "X".  
  
3.  Bestimmen Sie die Länge der noch nicht mit Nullen aufgefüllten numerischen Zeichenfolge, indem Sie die `ToString("D").Length`- oder die `ToString("X").Length`-Methode des Ganzzahlwerts aufrufen.  
  
4.  Fügen Sie die Anzahl der führenden Nullen, die in die formatierte Zeichenfolge eingefügt werden sollen, zur Länge der nicht aufgefüllten numerischen Zeichenfolge hinzu. Dies ergibt die Gesamtlänge der mit Nullen aufgefüllten Zeichenfolge.  
  
5.  Rufen Sie die `ToString(String)`-Methode des Ganzzahlwerts auf, und übergeben Sie die Zeichenfolge „D*n*“ für Dezimalzeichenfolgen und „X*n*“ für Hexadezimalzeichenfolgen, wobei *n* die Gesamtlänge der aufgefüllten Zeichenfolge darstellt. Sie können die Formatzeichenfolge „D*n*“ oder „X*n*“ auch in Methoden verwenden, die die kombinierte Formatierung unterstützen.  
  
 Im folgenden Beispiel wird ein Ganzzahlwert mit fünf führenden Nullen aufgefüllt.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a>Numerischen Wert bis zu einer bestimmten Länge mit führenden Nullen auffüllen  
  
1.  Bestimmen Sie, über wie viele Ziffern links des Dezimaltrennzeichens die Zeichenfolgendarstellung der Zahl verfügen soll. Schließen Sie alle führenden Nullen in diese Gesamtzahl der Ziffern ein.  
  
2.  Definieren Sie eine benutzerdefinierte numerische Formatzeichenfolge, in der die Mindestanzahl an Nullen mit dem Null-Platzhalter ("0") dargestellt wird.  
  
3.  Rufen Sie die `ToString(String)`-Methode der Zahl auf und übergeben sie die benutzerdefinierte Formatzeichenfolge. Sie können die benutzerdefinierte Formatzeichenfolge auch mit Methoden verwenden, die kombinierte Formatierung unterstützen.  
  
 Im folgenden Beispiel sind mehrere numerische Werte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Ziffern links des Dezimaltrennzeichens beträgt.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a>Numerischen Wert mit einer bestimmten Anzahl führender Nullen auffüllen  
  
1.  Bestimmen Sie, über wie viele führende Nullen der numerische Wert verfügen soll.  
  
2.  Bestimmen Sie die Anzahl der Ziffern links des Dezimaltrennzeichens in der nicht aufgefüllten numerischen Zeichenfolge. Gehen Sie dazu wie folgt vor:  
  
    1.  Bestimmen Sie, ob die Zeichenfolgendarstellung der Zahl ein Symbol für das Dezimaltrennzeichen beinhaltet.  
  
    2.  Wenn sie ein Dezimaltrennzeichen enthält, bestimmen Sie die Anzahl der Zeichen links des Dezimaltrennzeichens.  
  
         - oder -   
  
         Wenn sie kein Dezimaltrennzeichen enthält, bestimmen Sie die Länge der Zeichenfolge.  
  
3.  Erstellen Sie eine benutzerdefinierte Formatzeichenfolge, in der die gewünschte Anzahl führender Nullen in der Zeichenfolge mit dem Null-Platzhalter ("0") und die Ziffern in der Standardzeichenfolge mit dem Null-Platzhalter ("0") oder dem Ziffernplatzhalter ("#") angegeben werden.  
  
4.  Übergeben Sie die benutzerdefinierte Formatzeichenfolge als Parameter an die `ToString(String)`-Methode der Zahl oder an eine Methode, die kombinierte Formatierung unterstützt.  
  
 Im folgenden Beispiel werden zwei <xref:System.Double>-Werte mit fünf führenden Nullen aufgefüllt.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md)  
 [Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md)  
 [Kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md)
