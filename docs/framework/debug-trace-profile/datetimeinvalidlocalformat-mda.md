---
title: "dateTimeInvalidLocalFormat MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "dates [.NET Framework], formatting"
  - "invalid date time local format"
  - "invalid local formats"
  - "MDAs (managed debugging assistants), invalid local formats"
  - "managed debugging assistants (MDAs), invalid local formats"
  - "dateTimeInvalidLocalFormat MDA"
  - "date formatting"
  - "time formatting"
  - "UTC formatting"
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# dateTimeInvalidLocalFormat MDA
Der `dateTimeInvalidLocalFormat`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn eine <xref:System.DateTime>\-Instanz, die als UTC \(Universal Coordinated Time, koordinierte Weltzeit\) gespeichert ist, mit einem Format formatiert wird, das nur für lokale <xref:System.DateTime>\-Instanzen verwendet werden soll.  Dieser MDA wird nicht für nicht spezifizierte oder <xref:System.DateTime>\-Standardinstanzen aktiviert.  
  
## Symptom  
 Eine Anwendung serialisiert manuell eine <xref:System.DateTime>\-UTC\-Instanz unter Verwendung eines lokalen Formats:  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### Ursache  
 Das 'z'\-Format der <xref:System.DateTime.ToString%2A?displayProperty=fullName>\-Methode enthält die Abweichung der lokalen Zeitzone, z. B. "\+10:00" für die australische Zeit.  Daher wird nur ein sinnvolles Ergebnis erzielt, wenn der Wert der <xref:System.DateTime> lokal ist.  Wenn der Wert eine UTC\-Zeit ist, enthält <xref:System.DateTime.ToString%2A?displayProperty=fullName> die Abweichung der lokalen Zeitzone. Die Zeitzoneangabe wird aber weder angezeigt noch angepasst.  
  
### Lösung  
 <xref:System.DateTime>\-UTC\-Instanzen sollten auf eine Weise formatiert werden, aus der ersichtlich ist, dass es sich um UTC handelt.  Es wird empfohlen, ein 'Z' zu verwenden, um die UTC\-Zeit anzugeben:  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 Es ist außerdem ein "o"\-Format vorhanden, mit der eine <xref:System.DateTime> unter Verwendung der <xref:System.DateTime.Kind%2A>\-Eigenschaft serialisiert wird. Unabhängig davon, ob die Instanz lokal, UTC oder nicht spezifiziert ist, wird hierbei sichergestellt, dass die Serialisierung richtig erfolgt:  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA beeinflusst die Laufzeit nicht.  
  
## Ausgabe  
 Bei der Aktivierung dieses MDA erfolgt keine besondere Ausgabe. Die Aufrufliste kann jedoch verwendet werden, um festzustellen, wo sich der Aufruf von <xref:System.DateTime.ToString%2A> befindet, der den MDA aktiviert hat.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## Beispiel  
 Beispiel: In einer Anwendung wird wie im Folgenden gezeigt ein <xref:System.DateTime>\-UTC\-Wert indirekt mithilfe der <xref:System.Xml.XmlConvert>\-Klasse oder der <xref:System.Data.DataSet>\-Klasse serialisiert.  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 Die Serialisierungen mit <xref:System.Xml.XmlConvert> und <xref:System.Data.DataSet> verwenden in der Standardeinstellung das lokale Format für die Serialisierung.  Zusätzliche Optionen sind erforderlich, um andere Arten von <xref:System.DateTime>\-Werten zu serialisieren, z. B. UTC.  
  
 Übergeben Sie im vorliegenden Beispiel `XmlDateTimeSerializationMode.RoundtripKind` an den Aufruf von `ToString` für `XmlConvert`.  Dadurch werden die Daten als UTC\-Zeit serialisiert.  
  
 Wenn Sie ein <xref:System.Data.DataSet> verwenden, legen Sie die <xref:System.Data.DataColumn.DateTimeMode%2A>\-Eigenschaft des <xref:System.Data.DataColumn>\-Objekts auf <xref:System.Data.DataSetDateTime> fest.  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,   
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## Siehe auch  
 <xref:System.Globalization.DateTimeFormatInfo>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)