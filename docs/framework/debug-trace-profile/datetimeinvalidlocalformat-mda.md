---
title: DateTimeInvalidLocalFormat-MDA
description: Überprüfen Sie den DateTimeInvalidLocalFormat Managed Debug Assistant (MDA), der aktiviert wird, wenn ein UTC-gespeicherter DateTime-Wert ein lokales DateTime-Format erhält.
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
ms.openlocfilehash: ed2cf0b960c0a8f51dc327a5c58770fcf5e2fa17
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286057"
---
# <a name="datetimeinvalidlocalformat-mda"></a><span data-ttu-id="28b00-103">DateTimeInvalidLocalFormat-MDA</span><span class="sxs-lookup"><span data-stu-id="28b00-103">dateTimeInvalidLocalFormat MDA</span></span>

<span data-ttu-id="28b00-104">Der `dateTimeInvalidLocalFormat`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine als UTC (Universal Coordinated Time, koordinierte Weltzeit) gespeicherte <xref:System.DateTime>-Instanz mit einem Format formatiert wird, das nur für lokale <xref:System.DateTime>-Instanzen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="28b00-104">The `dateTimeInvalidLocalFormat` MDA is activated when a <xref:System.DateTime> instance that is stored as a Universal Coordinated Time (UTC) is formatted using a format that is intended to be used only for local <xref:System.DateTime> instances.</span></span> <span data-ttu-id="28b00-105">Dieser MDA wird nicht für nicht angegebene oder <xref:System.DateTime>-Standardinstanzen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="28b00-105">This MDA is not activated for unspecified or default <xref:System.DateTime> instances.</span></span>  
  
## <a name="symptom"></a><span data-ttu-id="28b00-106">Symptom</span><span class="sxs-lookup"><span data-stu-id="28b00-106">Symptom</span></span>  

 <span data-ttu-id="28b00-107">Eine Anwendung führt für eine <xref:System.DateTime>-UTC-Instanz eine manuelle Serialisierung mit einem lokalen Format durch:</span><span class="sxs-lookup"><span data-stu-id="28b00-107">An application is manually serializing a UTC <xref:System.DateTime> instance using a local format:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### <a name="cause"></a><span data-ttu-id="28b00-108">Ursache</span><span class="sxs-lookup"><span data-stu-id="28b00-108">Cause</span></span>  

 <span data-ttu-id="28b00-109">Das „z“-Format der <xref:System.DateTime.ToString%2A?displayProperty=nameWithType>-Methode beinhaltet die Abweichung der lokalen Zeitzone, beispielsweise „+ 10:00“ für Ortszeit Sydney.</span><span class="sxs-lookup"><span data-stu-id="28b00-109">The 'z' format for the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> method includes the local time zone offset, for example, "+10:00" for Sydney time.</span></span> <span data-ttu-id="28b00-110">Daher wird nur ein aussagekräftiges Ergebnis erzielt, wenn der Wert für <xref:System.DateTime> lokal ist.</span><span class="sxs-lookup"><span data-stu-id="28b00-110">As such, it will only produce a meaningful result if the value of the <xref:System.DateTime> is local.</span></span> <span data-ttu-id="28b00-111">Gibt der Wert die UTC-Zeit an, beinhaltet <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> zwar die Abweichung der lokalen Zeitzone, der Zeitzonenbezeichner wird aber weder angezeigt noch angepasst.</span><span class="sxs-lookup"><span data-stu-id="28b00-111">If the value is UTC time, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> includes the local time zone offset, but it does not display or adjust the time zone specifier.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="28b00-112">Lösung</span><span class="sxs-lookup"><span data-stu-id="28b00-112">Resolution</span></span>  

 <span data-ttu-id="28b00-113"><xref:System.DateTime>-UTC-Instanzen sollten so formatiert werden, dass sie als UTC erkennbar sind.</span><span class="sxs-lookup"><span data-stu-id="28b00-113">UTC <xref:System.DateTime> instances should be formatted in a way that indicates that they are UTC.</span></span> <span data-ttu-id="28b00-114">Es wird empfohlen, für die Angabe von UTC-Zeiten ein „Z“ zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="28b00-114">The recommended format for UTC times to use a 'Z' to denote UTC time:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 <span data-ttu-id="28b00-115">Zudem existiert ein „o“-Format, mit dem eine <xref:System.DateTime> mithilfe der <xref:System.DateTime.Kind%2A>-Eigenschaft serialisiert werden kann. Diese Eigenschaft führt unabhängig davon, ob die Instanz lokal, UTC oder nicht angegeben ist, eine korrekte Serialisierung durch:</span><span class="sxs-lookup"><span data-stu-id="28b00-115">There is also an "o" format that serializes a <xref:System.DateTime> making use of the <xref:System.DateTime.Kind%2A> property that serializes correctly regardless of whether the instance is local, UTC, or unspecified:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="28b00-116">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="28b00-116">Effect on the Runtime</span></span>  

 <span data-ttu-id="28b00-117">Dieser MDA hat keine Auswirkungen auf die Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="28b00-117">This MDA does not affect the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="28b00-118">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="28b00-118">Output</span></span>  

 <span data-ttu-id="28b00-119">Das Aktivieren dieses MDA erzeugt keine besondere Ausgabe. Die Aufrufliste kann jedoch zur Bestimmung des Speicherorts für den <xref:System.DateTime.ToString%2A>-Aufruf verwendet werden, der den MDA aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="28b00-119">There is no special output as a result of this MDA activating., However, the call stack can be used to determine the location of the <xref:System.DateTime.ToString%2A> call that activated the MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="28b00-120">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="28b00-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="28b00-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28b00-121">Example</span></span>  

 <span data-ttu-id="28b00-122">In einer Anwendung wird wie im Folgenden gezeigt eine indirekte Serialisierung für einen <xref:System.DateTime>-UTC-Wert mithilfe der Klasse <xref:System.Xml.XmlConvert> oder <xref:System.Data.DataSet> durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="28b00-122">Consider an application that is indirectly serializing a UTC <xref:System.DateTime> value by using the <xref:System.Xml.XmlConvert> or <xref:System.Data.DataSet> class, in the following manner.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 <span data-ttu-id="28b00-123">Die Serialisierungen mit <xref:System.Xml.XmlConvert> und <xref:System.Data.DataSet> verwenden standardmäßig lokale Formate zur Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="28b00-123">The <xref:System.Xml.XmlConvert> and <xref:System.Data.DataSet> serializations use local formats for serialization by default.</span></span> <span data-ttu-id="28b00-124">Zusätzliche Optionen sind erforderlich, um andere Arten von <xref:System.DateTime>-Werten, z.B. UTC, zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="28b00-124">Additional options are required to serialize other kinds of <xref:System.DateTime> values, such as UTC.</span></span>  
  
 <span data-ttu-id="28b00-125">Übergeben Sie im vorliegenden Beispiel `XmlDateTimeSerializationMode.RoundtripKind` an den Aufruf von `ToString` für `XmlConvert`.</span><span class="sxs-lookup"><span data-stu-id="28b00-125">For this specific example, pass in `XmlDateTimeSerializationMode.RoundtripKind` to the `ToString` call on `XmlConvert`.</span></span> <span data-ttu-id="28b00-126">Dadurch werden die Daten als UTC-Zeit serialisiert.</span><span class="sxs-lookup"><span data-stu-id="28b00-126">This serializes the data as a UTC time.</span></span>  
  
 <span data-ttu-id="28b00-127">Bei Verwendung von <xref:System.Data.DataSet> legen Sie die <xref:System.Data.DataColumn.DateTimeMode%2A>-Eigenschaft des <xref:System.Data.DataColumn>-Objekts auf <xref:System.Data.DataSetDateTime.Utc> fest.</span><span class="sxs-lookup"><span data-stu-id="28b00-127">If using a <xref:System.Data.DataSet>, set the <xref:System.Data.DataColumn.DateTimeMode%2A> property on the <xref:System.Data.DataColumn> object to <xref:System.Data.DataSetDateTime.Utc>.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## <a name="see-also"></a><span data-ttu-id="28b00-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28b00-128">See also</span></span>

- <xref:System.Globalization.DateTimeFormatInfo>
- [<span data-ttu-id="28b00-129">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="28b00-129">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
