---
title: "Verwenden von Standardausnahmetypen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Auslösen von Ausnahmen, Standardtypen"
  - "Abfangen von Ausnahmen"
  - "Abfangen von Ausnahmen"
  - "Auslösen von Ausnahmen"
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# Verwenden von Standardausnahmetypen
Dieser Abschnitt beschreibt die Standardausnahmen, die durch das Framework und die Details ihrer Verwendung bereitgestellt. Die Liste ist nicht vollständig. Sie finden Sie in der .NET Framework\-Referenzdokumentation für die Verwendung der anderen Framework\-Ausnahmetypen.  
  
## Exception und SystemException  
 **X nicht** auslösen <xref:System.Exception?displayProperty=fullName> oder <xref:System.SystemException?displayProperty=fullName>.  
  
 **X nicht** catch `System.Exception` oder `System.SystemException` in Frameworkcode, es sei denn, Sie erneut auslösen möchten.  
  
 **X vermeiden** Abfangen von `System.Exception` oder `System.SystemException`, außer im Ausnahmehandler der obersten Ebene.  
  
## ApplicationException  
 **X nicht** auslösen oder eine Ableitung von <xref:System.ApplicationException>.  
  
## InvalidOperationException  
 **✓ führen** Auslösen einer <xref:System.InvalidOperationException> wenn das Objekt in einem unzulässigen Zustand befindet.  
  
## ArgumentException, ArgumentNullException und ArgumentOutOfRangeException  
 **✓ führen** auslösen <xref:System.ArgumentException> oder einem seiner Untertypen, wenn ungültige Argumente an einen Member übergeben werden. Möchten Sie am weitesten abgeleiteten Ausnahmetyp, falls zutreffend.  
  
 **✓ führen** legen Sie die `ParamName` Eigenschaft beim Auslösen einer der Unterklassen von `ArgumentException`.  
  
 Diese Eigenschaft stellt den Namen des Parameters, der die Ausnahme ausgelöst hat. Beachten Sie, dass die Eigenschaft mit einer der Konstruktorüberladungen festgelegt werden kann.  
  
 **✓ führen** verwenden `value` für den Namen des impliziten Wertparameters von Eigenschaftensettern.  
  
## NullReferenceException IndexOutOfRangeException und AccessViolationException  
 **X nicht** dass öffentlich aufrufbare APIs explizit oder implizit auslösen <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, oder <xref:System.IndexOutOfRangeException>. Diese Ausnahmen sind reserviert und das Ausführungsmodul ausgelöst und in den meisten Fällen einen Fehler anzugeben.  
  
 Führen Sie die Überprüfung, um zu vermeiden, diese Ausnahmen auslösen. Diese Ausnahmen auslösen stellt Details zur Implementierung der Methode, die mit der Zeit ändern können.  
  
## StackOverflowException  
 **X nicht** Explizites Auslösen von <xref:System.StackOverflowException>. Diese Ausnahme sollte nur von der CLR explizit ausgelöst werden.  
  
 **X nicht** catch `StackOverflowException`.  
  
 Es ist fast unmöglich, verwalteten Code zu schreiben, die in beliebigen Stapelüberläufe konsistent bleiben. Prüfpunkte zum Verschieben von klar definierten stellen Stapelüberläufe über statt aus beliebigen Stapelüberläufe Rückgängigmachen bleiben der nicht verwalteten Teile der CLR konsistent.  
  
## OutOfMemoryException  
 **X nicht** Explizites Auslösen von <xref:System.OutOfMemoryException>. Diese Ausnahme wird nur von der CLR\-Infrastruktur ausgelöst werden.  
  
## ComException und SEHException ExecutionEngineException  
 **X nicht** Explizites Auslösen von <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, und <xref:System.Runtime.InteropServices.SEHException>. Diese Ausnahmen werden nur von der CLR\-Infrastruktur ausgelöst werden.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)