---
title: "Gewusst wie: Konvertieren einer Zeichenfolge in einen DateTime-Wert (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Zeichenfolgen [C#], Konvertieren in DateTime"
ms.assetid: 88abef11-3a06-4b49-8dd2-61ed0e876fc3
caps.latest.revision: 21
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Konvertieren einer Zeichenfolge in einen DateTime-Wert (C#-Programmierhandbuch)
Es ist in Programmen üblich, Benutzern die Eingabe von Datumsangaben als Zeichenfolgenwerte zu ermöglichen. Um ein zeichenfolgenbasiertes Datum in ein <xref:System.DateTime?displayProperty=fullName>\-Objekt zu konvertieren, können Sie die <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=fullName>\-Methode oder die statische <xref:System.DateTime.Parse%28System.String%29?displayProperty=fullName>\-Methode verwenden, wie im folgenden Beispiel dargestellt.  
  
 **Kultur**.  Datumsangaben werden weltweit je nach Kultur unterschiedlich geschrieben.  In den USA entspricht 01\/20\/2008 z. B. dem 20. Januar 2008.  In Frankreich wird dadurch eine InvalidFormatException ausgelöst. Dies liegt daran, dass Datumsangaben in Frankreich als Tag\/Monat\/Jahr und in den USA als Monat\/Tag\/Jahr gelesen werden.  
  
 Daher wird eine Zeichenfolge wie 20\/01\/2008 in Frankreich als 20. Januar 2008 interpretiert, während sie in den USA eine InvalidFormatException auslöst.  
  
 Zum Ermitteln der aktuellen Kultureinstellungen können Sie System.Globalization.CultureInfo.CurrentCulture verwenden.  
  
 Im Folgenden finden Sie ein einfaches Beispiel für das Konvertieren einer Zeichenfolge in dateTime.  
  
 Weitere Beispiele für Datumszeichenfolgen finden Sie unter <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=fullName>.  
  
```vb  
string dateTime = "01/08/2008 14:50:50.42"; DateTime dt = Convert.ToDateTime(dateTime); Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}", dt.Year, dt.Month, dt.Day, dt.Hour, dt.Minute, dt.Second, dt.Millisecond); // Specify exactly how to interpret the string. IFormatProvider culture = new System.Globalization.CultureInfo("fr-FR", true); // Alternate choice: If the string has been input by an end user, you might // want to format it according to the current culture: // IFormatProvider culture = System.Threading.Thread.CurrentThread.CurrentCulture; DateTime dt2 = DateTime.Parse(dateTime, culture, System.Globalization.DateTimeStyles.AssumeLocal); Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}", dt2.Year, dt2.Month, dt2.Day, dt2.Hour, dt2.Minute, dt2.Second, dt2.Millisecond /* Output (assuming first culture is en-US and second is fr-FR): Year: 2008, Month: 1, Day: 8, Hour: 14, Minute: 50, Second: 50, Millisecond: 420 Year: 2008, Month: 8, Day: 1, Hour: 14, Minute: 50, Second: 50, Millisecond: 420 Press any key to continue . . . */  
```  
  
## Beispiel  
 [!code-cs[csProgGuideStrings#13](../../../csharp/programming-guide/strings/codesnippet/CSharp/CSRefStrings/Strings.cs#13)]  
  
## Siehe auch  
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)