---
title: DateTimeInvalidLocalFormat-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- dates [.NET Framework], formatting
- invalid date time local format
- invalid local formats
- MDAs (managed debugging assistants), invalid local formats
- managed debugging assistants (MDAs), invalid local formats
- dateTimeInvalidLocalFormat MDA
- date formatting
- time formatting
- UTC formatting
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
ms.openlocfilehash: b01f030c474e426cb87fb907f99f241eeb76a7fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174757"
---
# <a name="datetimeinvalidlocalformat-mda"></a>DateTimeInvalidLocalFormat-MDA
Der `dateTimeInvalidLocalFormat`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine als UTC (Universal Coordinated Time, koordinierte Weltzeit) gespeicherte <xref:System.DateTime>-Instanz mit einem Format formatiert wird, das nur für lokale <xref:System.DateTime>-Instanzen verwendet werden soll. Dieser MDA wird nicht für nicht angegebene oder <xref:System.DateTime>-Standardinstanzen aktiviert.  
  
## <a name="symptom"></a>Symptom  
 Eine Anwendung führt für eine <xref:System.DateTime>-UTC-Instanz eine manuelle Serialisierung mit einem lokalen Format durch:  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### <a name="cause"></a>Ursache  
 Das „z“-Format der <xref:System.DateTime.ToString%2A?displayProperty=nameWithType>-Methode beinhaltet die Abweichung der lokalen Zeitzone, beispielsweise „+ 10:00“ für Ortszeit Sydney. Daher wird nur ein aussagekräftiges Ergebnis erzielt, wenn der Wert für <xref:System.DateTime> lokal ist. Gibt der Wert die UTC-Zeit an, beinhaltet <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> zwar die Abweichung der lokalen Zeitzone, der Zeitzonenbezeichner wird aber weder angezeigt noch angepasst.  
  
### <a name="resolution"></a>Lösung  
 <xref:System.DateTime>-UTC-Instanzen sollten so formatiert werden, dass sie als UTC erkennbar sind. Es wird empfohlen, für die Angabe von UTC-Zeiten ein „Z“ zu verwenden:  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 Zudem existiert ein „o“-Format, mit dem eine <xref:System.DateTime> mithilfe der <xref:System.DateTime.Kind%2A>-Eigenschaft serialisiert werden kann. Diese Eigenschaft führt unabhängig davon, ob die Instanz lokal, UTC oder nicht angegeben ist, eine korrekte Serialisierung durch:  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die Laufzeit.  
  
## <a name="output"></a>Output  
 Das Aktivieren dieses MDA erzeugt keine besondere Ausgabe. Die Aufrufliste kann jedoch zur Bestimmung des Speicherorts für den <xref:System.DateTime.ToString%2A>-Aufruf verwendet werden, der den MDA aktiviert hat.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Beispiel  
 In einer Anwendung wird wie im Folgenden gezeigt eine indirekte Serialisierung für einen <xref:System.DateTime>-UTC-Wert mithilfe der Klasse <xref:System.Xml.XmlConvert> oder <xref:System.Data.DataSet> durchgeführt:  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 Die Serialisierungen mit <xref:System.Xml.XmlConvert> und <xref:System.Data.DataSet> verwenden standardmäßig lokale Formate zur Serialisierung. Zusätzliche Optionen sind erforderlich, um andere Arten von <xref:System.DateTime>-Werten, z.B. UTC, zu serialisieren.  
  
 Übergeben Sie im vorliegenden Beispiel `XmlDateTimeSerializationMode.RoundtripKind` an den Aufruf von `ToString` für `XmlConvert`. Dadurch werden die Daten als UTC-Zeit serialisiert.  
  
 Bei Verwendung von <xref:System.Data.DataSet> legen Sie die <xref:System.Data.DataColumn.DateTimeMode%2A>-Eigenschaft des <xref:System.Data.DataColumn>-Objekts auf <xref:System.Data.DataSetDateTime.Utc> fest.  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Globalization.DateTimeFormatInfo>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](diagnosing-errors-with-managed-debugging-assistants.md)
