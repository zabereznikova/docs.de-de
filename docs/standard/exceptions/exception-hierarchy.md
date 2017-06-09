---
title: "Ausnahmenhierarchie | Microsoft Docs"
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
  - "Ausnahmen, Typen"
  - "Laufzeit, Ausnahmen"
  - "Basisausnahmen"
  - "ApplicationException-Klasse"
  - "Common Language Runtime und Ausnahmen"
  - "COM-interop, Ausnahmen"
  - "Ausnahmen und Hierarchien"
ms.assetid: f7d68675-be06-40fb-a555-05f0c5a6f66b
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# Ausnahmenhierarchie
Es gibt zwei Arten von Ausnahmen: Ausnahmen, die von einem aktiven Programm generiert werden, und Ausnahmen, die von der Common Language Runtime (CLR) generiert werden. Darüber hinaus gibt es eine Hierarchie von Ausnahmen, die von einer Anwendung oder der Runtime ausgelöst werden können.  
  
 Die <xref:System.Exception?displayProperty=fullName> Klasse ist die Basisklasse für Ausnahmen. Verschiedene Ausnahmeklassen erben direkt von <xref:System.Exception>, einschließlich <xref:System.ApplicationException> und <xref:System.SystemException>. Diese beiden Klassen bilden die Grundlage für fast alle Laufzeitausnahmen (Runtime-Ausnahmen).  
  
 Die meisten Ausnahmen, die direkte Ableitung <xref:System.Exception> keine Funktion und keine neue Mitglieder hinzufügen. Zum Beispiel die <xref:System.InvalidCastException> Klassenhierarchie lautet wie folgt:  
  
 <xref:System.Object> <xref:System.Exception> <xref:System.SystemException> <xref:System.InvalidCastException>  
  
 Löst die Laufzeit die entsprechende abgeleitete Klasse von <xref:System.SystemException> Wenn Fehler auftreten. Diese Fehler werden durch fehlgeschlagene Laufzeitüberprüfungen verursacht (z. B. das Verlassen des gültigen Bereichs eines Arrays) und können bei der Ausführung einer Methode auftreten. Wenn Sie eine Anwendung, die neue Ausnahmen erstellt entwerfen, sollten Sie diese Ausnahmen von Ableiten der <xref:System.Exception> Klasse. Es wird nicht empfohlen, dass Sie erfassen einer <xref:System.SystemException>, noch ist es guter Programmierstil, löst einen <xref:System.SystemException> in Ihrer Anwendung.  
  
 Die Ausnahmen, die von der Common Language Runtime oder ein nicht behebbarer Fehler ausgelöst: enthalten <xref:System.ExecutionEngineException>, <xref:System.StackOverflowException>, und <xref:System.OutOfMemoryException>.  
  
 Abgeleitet von <xref:System.SystemException> und weitere erweitert werden, indem <xref:System.Runtime.InteropServices.ExternalException>. Beispielsweise <xref:System.Runtime.InteropServices.COMException> wird der Ausnahmefehler während COM-Interop-Operationen und leitet sich von <xref:System.Runtime.InteropServices.ExternalException>. <xref:System.ComponentModel.Win32Exception> und <xref:System.Runtime.InteropServices.SEHException> auch abgeleitet <xref:System.Runtime.InteropServices.ExternalException>.  
  
## <a name="hierarchy-of-runtime-exceptions"></a>Hierarchie der Runtime-Ausnahmen  
 Die Common Language Runtime verfügt über einen Basissatz von Ausnahmen, die von <xref:System.SystemException> , dass es für die Ausführung einzelne Anweisungen auslöst. In der folgenden Tabelle sind in hierarchischer Reihenfolge die Standardausnahmen, die von der Runtime bereitgestellt werden, sowie die Bedingungen aufgeführt, unter denen eine abgeleitete Klasse erstellt werden sollte.  
  
|Ausnahmetyp|Basistyp|Beschreibung|Beispiel|  
|--------------------|---------------|-----------------|-------------|  
|[Ausnahme](../../../docs/standard/exceptions/exception-class-and-properties.md)|<xref:System.Object>|Die Basisklasse für alle Ausnahmen.|Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme).|  
|<xref:System.SystemException>|<xref:System.Exception>|Basisklasse für alle von der Runtime generierten Fehler.|Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme).|  
|<xref:System.IndexOutOfRangeException>|<xref:System.SystemException>|Wird von der Runtime nur dann ausgelöst, wenn ein Array falsch indiziert ist.|Indizieren eines Arrays außerhalb seines gültigen Vereichs:<br /><br /> `var i = arr[arr.Length + 1];`<br /><br /> `Dim i = arr(arr.Length + 1)`|  
|<xref:System.NullReferenceException>|<xref:System.SystemException>|Wird von der Runtime nur dann ausgelöst, wenn auf ein NULL-Objekt verwiesen wird.|`object o = null; string s = o.ToString();`<br /><br /> `Dim o As Object = Nothing Dim s As String = o.ToString()`|  
|<xref:System.AccessViolationException>|<xref:System.SystemException>|Wird von der Runtime nur dann ausgelöst, wenn auf ungültigen Speicher zugegriffen wird.|Tritt auf, wenn nicht verwalteter Code oder unsicherer verwalteter Code aufgerufen und ein ungültiger Zeiger verwendet wird.|  
|<xref:System.InvalidOperationException>|<xref:System.SystemException>|Wird von Methoden ausgelöst, wenn ein ungültiger Status vorliegt.|Aufrufen des Enumerators `GetNext` -Methode nach dem Entfernen eines Elements aus der zugrunde liegenden Auflistung.|  
|<xref:System.ArgumentException>|<xref:System.SystemException>|Die Basisklasse für alle Argumentausnahmen.|Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme).|  
|<xref:System.ArgumentNullException>|<xref:System.ArgumentException>|Wird von Methoden ausgelöst, bei denen ein Argument nicht gleich NULL sein darf.|`String s = null; int i = "Calculate".IndexOf(s);`<br /><br /> `Dim s As String = Nothing Dim i As Integer = "Calculate".IndexOf(s)`|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.ArgumentException>|Wird von Methoden ausgelöst, die überprüfen, ob Argumente in einem angegebenen Bereich liegen.|`String s = "string"; s = s.Substring(s.Length + 1);`<br /><br /> `Dim s As String = "string" s = s.Substring(s.Length + 1)`|  
|<xref:System.Runtime.InteropServices.ExternalException>|<xref:System.SystemException>|Basisklasse für Ausnahmen, die in Umgebungen auftreten oder für Umgebungen vorgesehen sind, die sich außerhalb der Runtime befinden.|Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme).|  
|<xref:System.Runtime.InteropServices.COMException>|<xref:System.Runtime.InteropServices.ExternalException>|Ausnahme, die Informationen über COM-HRESULT kapselt.|Wird in COM-Interop verwendet.|  
|<xref:System.Runtime.InteropServices.SEHException>|<xref:System.Runtime.InteropServices.ExternalException>|Ausnahme, die Informationen über Win32-SEH (Structured Exception Handling) kapselt.|Wird im Zusammenspiel mit nicht verwaltetem Code verwendet.|  
  
## <a name="see-also"></a>Siehe auch  
 [Exception-Klasse und Eigenschaften](../../../docs/standard/exceptions/exception-class-and-properties.md)   
 [Grundlagen der Ausnahmebehandlung](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [Best Practices für Ausnahmen](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [Ausnahmen](../../../docs/standard/exceptions/index.md)