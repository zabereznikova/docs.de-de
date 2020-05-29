---
title: Verbindungszeichenfolgen
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 3f56a487121757706ef6b4dfd11fcd761657431a
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202278"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="32ce6-102">Verbindungszeichenfolgen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="32ce6-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="32ce6-103">Eine Verbindungszeichenfolge enthält Initialisierungsinformationen, die als Parameter von einem Datenanbieter an eine Datenquelle übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="32ce6-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="32ce6-104">Der Datenanbieter empfängt die Verbindungs Zeichenfolge als Wert der- <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="32ce6-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="32ce6-105">Der Anbieter analysiert die Verbindungs Zeichenfolge und stellt sicher, dass die Syntax korrekt ist und dass die Schlüsselwörter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="32ce6-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="32ce6-106">Anschließend übergibt die- <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> Methode die analysierten Verbindungsparameter an die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="32ce6-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="32ce6-107">Die Datenquelle führt eine weitere Validierung durch und stellt eine Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="32ce6-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="32ce6-108">Syntax von Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="32ce6-108">Connection string syntax</span></span>

<span data-ttu-id="32ce6-109">Eine Verbindungs Zeichenfolge ist eine durch Semikolons getrennte Liste von Schlüssel-Wert-Parameter Paaren:</span><span class="sxs-lookup"><span data-stu-id="32ce6-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```csharp
keyword1=value; keyword2=value;
```

<span data-ttu-id="32ce6-110">Bei Schlüsselwörtern muss die Groß-/Kleinschreibung nicht beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="32ce6-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="32ce6-111">Bei Werten kann jedoch abhängig von der Datenquelle die Groß-/Kleinschreibung beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="32ce6-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="32ce6-112">Sowohl Schlüsselwörter als auch Werte können [Leerzeichen](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)enthalten.</span><span class="sxs-lookup"><span data-stu-id="32ce6-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="32ce6-113">Führende und nachfolgende Leerzeichen werden in Schlüsselwörtern und Werten ohne Anführungszeichen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="32ce6-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="32ce6-114">Wenn ein Wert das Semikolon oder [Unicode-Steuerzeichen](https://en.wikipedia.org/wiki/Unicode_control_characters)oder führende oder nachfolgende Leerzeichen enthält, muss er in einfache oder doppelte Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="32ce6-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="32ce6-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="32ce6-115">For example:</span></span>

```csharp
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="32ce6-116">Das einschließende Zeichen darf nicht innerhalb des umschließenden Werts auftreten.</span><span class="sxs-lookup"><span data-stu-id="32ce6-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="32ce6-117">Daher kann ein Wert, der einfache Anführungszeichen enthält, nur in doppelte Anführungszeichen eingeschlossen werden und umgekehrt:</span><span class="sxs-lookup"><span data-stu-id="32ce6-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```csharp
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="32ce6-118">Sie können das einschließende Zeichen auch mit Escapezeichen versehen, indem Sie zwei davon verwenden:</span><span class="sxs-lookup"><span data-stu-id="32ce6-118">You can also escape the enclosing character by using two of them together:</span></span>

```csharp
Keyword="double""quotation";
Keyword='single''quotation';
```

<span data-ttu-id="32ce6-119">Die Anführungszeichen selbst und das Gleichheitszeichen erfordern keinen Escapezeichen, sodass die folgenden Verbindungs Zeichenfolgen gültig sind:</span><span class="sxs-lookup"><span data-stu-id="32ce6-119">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```csharp
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="32ce6-120">Da jeder Wert bis zum nächsten Semikolon oder Ende der Zeichenfolge gelesen wird, ist der Wert im letzteren Beispiel `a=b=c` , und das abschließende Semikolon ist optional.</span><span class="sxs-lookup"><span data-stu-id="32ce6-120">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="32ce6-121">Alle Verbindungs Zeichenfolgen haben dieselbe grundlegende Syntax, die oben beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="32ce6-121">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="32ce6-122">Der Satz der erkannten Schlüsselwörter hängt jedoch vom Anbieter ab und hat sich über die Jahre von früheren APIs wie *ODBC*entwickelt.</span><span class="sxs-lookup"><span data-stu-id="32ce6-122">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="32ce6-123">Der *.NET Framework* -Datenanbieter für *SQL Server* ( `SqlClient` ) unterstützt viele Schlüsselwörter aus älteren APIs, ist jedoch im Allgemeinen flexibler und akzeptiert Synonyme für viele der allgemeinen Schlüsselwörter der Verbindungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="32ce6-123">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="32ce6-124">Das Eingeben von Fehlern kann zu Fehlern führen.</span><span class="sxs-lookup"><span data-stu-id="32ce6-124">Typing mistakes can cause errors.</span></span> <span data-ttu-id="32ce6-125">Beispielsweise `Integrated Security=true` ist gültig, verursacht jedoch `IntegratedSecurity=true` einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="32ce6-125">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="32ce6-126">Verbindungs Zeichenfolgen, die zur Laufzeit von nicht validierten Benutzereingaben manuell erstellt werden, sind anfällig für Angriffe durch Zeichen folgen Injektion und gefährden die Sicherheit in der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="32ce6-126">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="32ce6-127">Um diese Probleme zu beheben, wurden von *ADO.net* 2,0 [Verbindungs Zeichenfolgen](connection-string-builders.md) -Generatoren für jeden *.NET Framework* -Datenanbieter eingeführt.</span><span class="sxs-lookup"><span data-stu-id="32ce6-127">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="32ce6-128">Diese Verbindungs Zeichenfolgen-Generatoren machen Parameter als stark typisierte Eigenschaften verfügbar und ermöglichen es, die Verbindungs Zeichenfolge zu validieren, bevor Sie an die Datenquelle gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="32ce6-128">These connection string builders expose parameters as strongly typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="32ce6-129">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="32ce6-129">In This Section</span></span>

<span data-ttu-id="32ce6-130">[Verbindungs Zeichen folgen-Generatoren](connection-string-builders.md)</span><span class="sxs-lookup"><span data-stu-id="32ce6-130">[Connection String Builders](connection-string-builders.md)</span></span>\
<span data-ttu-id="32ce6-131">Zeigt, wie mit den `ConnectionStringBuilder`-Klassen gültige Verbindungszeichenfolgen zur Laufzeit erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="32ce6-131">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="32ce6-132">[Verbindungs Zeichenfolgen und Konfigurationsdateien](connection-strings-and-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="32ce6-132">[Connection Strings and Configuration Files](connection-strings-and-configuration-files.md)</span></span>\
<span data-ttu-id="32ce6-133">Zeigt, wie Verbindungszeichenfolgen in Konfigurationsdateien gespeichert und abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="32ce6-133">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="32ce6-134">[Verbindungs Zeichen folgen Syntax](connection-string-syntax.md)</span><span class="sxs-lookup"><span data-stu-id="32ce6-134">[Connection String Syntax](connection-string-syntax.md)</span></span>\
<span data-ttu-id="32ce6-135">Beschreibt das Konfigurieren anbieterspezifischer Verbindungszeichenfolgen für `SqlClient`, `OracleClient`, `OleDb` und `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="32ce6-135">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="32ce6-136">[Schützen von Verbindungsinformationen](protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="32ce6-136">[Protecting Connection Information](protecting-connection-information.md)</span></span>\
<span data-ttu-id="32ce6-137">Demonstriert Verfahren zum Schützen von Informationen, die beim Herstellen von Verbindungen mit einer Datenquelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="32ce6-137">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="32ce6-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32ce6-138">See also</span></span>

- [<span data-ttu-id="32ce6-139">Herstellen der Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="32ce6-139">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="32ce6-140">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="32ce6-140">ADO.NET Overview</span></span>](ado-net-overview.md)
