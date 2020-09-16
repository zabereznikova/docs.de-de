---
title: Leitfaden für DataSet und Datentabelle
ms.date: 07/14/2020
dev_langs:
- csharp
ms.openlocfilehash: 34fb95e35e169ca0b72735a16539ecfdec037f87
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554540"
---
# <a name="dataset-and-datatable-security-guidance"></a>Leitfaden für DataSet und Datentabelle

Dieser Artikel bezieht sich auf:

* .NET Framework (alle Versionen)
* .Net Core und höher
* .NET 5.0 und höher

Bei [DataSets](/dotnet/api/system.data.dataset) und [Datentypen handelt](/dotnet/api/system.data.datatable) es sich um Legacy-.NET-Komponenten, die das darstellen von Datasets als verwaltete Objekte ermöglichen. Diese Komponenten wurden in .NET 1,0 als Teil der ursprünglichen ADO.net- [Infrastruktur](./index.md)eingeführt. Ihr Ziel bestand darin, eine verwaltete Sicht über ein relationales Dataset bereitzustellen und dabei zu abstrahieren, ob die zugrunde liegende Quelle der Daten XML, SQL oder eine andere Technologie war.

Weitere Informationen zu ADO.net, einschließlich modernerer Daten Ansichts Paradigmen, finden Sie in [der ADO.NET-Dokumentation](../index.md).

## <a name="default-restrictions-when-deserializing-a-dataset-or-datatable-from-xml"></a>Standard Einschränkungen beim Deserialisieren eines Datasets oder einer Datentabelle aus XML

Unter allen unterstützten Versionen von .NET Framework, .net Core und .net, `DataSet` und `DataTable` legen Sie die folgenden Einschränkungen für die Typen von Objekten in den deserialisierten Daten ab. Standardmäßig ist diese Liste auf Folgendes beschränkt:

* Primitive und primitive Entsprechungen: `bool` , `char` , `sbyte` , `byte` , `short` , `ushort` , `int` , `uint` , `long` , `ulong` , `float` , `double` , `decimal` , `DateTime` , `DateTimeOffset` , `TimeSpan` , `string` , `Guid` , `SqlBinary` , `SqlBoolean` , `SqlByte` , `SqlBytes` , `SqlChars` , `SqlDateTime` , `SqlDecimal` , `SqlDouble` , `SqlGuid` , `SqlInt16` , `SqlInt32` ,,, `SqlInt64` `SqlMoney` `SqlSingle` und `SqlString` .
* Häufig verwendete nicht primitive: `Type` , `Uri` und `BigInteger` .
* Häufig verwendete _System. Drawing_ -Typen: `Color` , `Point` , `PointF` , `Rectangle` , `RectangleF` , `Size` und `SizeF` .
* `Enum` solche.
* Arrays und Listen der oben genannten Typen.

Wenn die eingehenden XML-Daten ein Objekt enthalten, dessen Typ nicht in dieser Liste enthalten ist:

* Eine Ausnahme wird mit der folgenden Meldung und Stapel Überwachung ausgelöst.  
Fehlermeldung:  
System. InvalidOperationException: Type ' \<Type Name\> , Version = \<n.n.n.n\> , Culture = \<culture\> , PublicKeyToken = \<token value\> ' ist hier nicht zulässig. Weitere Informationen finden Sie unter [https://go.microsoft.com/fwlink/?linkid=2132227](https://go.microsoft.com/fwlink/?linkid=2132227) .  
Stapelüberwachung:  
bei System. Data. typelimiter. ensuretypeisallowed (Type type, typelimiter capturedlimiter)  
bei System. Data. datacolenn. updatecolumschlag Type (Type type, StorageType TypeCode)  
System. Data. datacolenumn. set_DataType (Typwert)  

* Der Deserialisierungsvorgang schlägt fehl.

Beim Laden von XML in eine vorhandene- `DataSet` Instanz oder- `DataTable` Instanz werden die vorhandenen Spaltendefinitionen ebenfalls berücksichtigt. Wenn die Tabelle bereits eine Spaltendefinition eines benutzerdefinierten Typs enthält, wird dieser Typ für die Dauer des XML-Deserialisierungsvorgangs vorübergehend zur Zulassungsliste hinzugefügt.

> [!NOTE]
> Wenn Sie einem Spalten hinzufügen `DataTable` , `ReadXml` liest das Schema nicht aus dem XML-Code, und wenn das Schema nicht mit dem Schema identisch ist, werden die Datensätze ebenfalls nicht gelesen, sodass Sie alle Spalten selbst hinzufügen müssen, um diese Methode zu verwenden.

```csharp
XmlReader xmlReader = GetXmlReader();

// Assume the XML blob contains data for type MyCustomClass.
// The following call to ReadXml fails because MyCustomClass isn't in the allowed types list.

DataTable table = new DataTable("MyDataTable");
table.ReadXml(xmlReader);

// However, the following call to ReadXml succeeds, since the DataTable instance
// already defines a column of type MyCustomClass.

DataTable table = new DataTable("MyDataTable");
table.Columns.Add("MyColumn", typeof(MyCustomClass));
table.ReadXml(xmlReader); // this call will succeed
```

Die Objekttyp Einschränkungen gelten auch, wenn verwendet wird `XmlSerializer` , um eine Instanz von oder zu deserialisieren `DataSet` `DataTable` . Sie sind jedoch möglicherweise nicht anwendbar, wenn Sie verwenden `BinaryFormatter` , um eine Instanz von oder zu deserialisieren `DataSet` `DataTable` .

Die Objekttyp Einschränkungen gelten nicht bei der Verwendung `DataAdapter.Fill` von, z. b. Wenn eine- `DataTable` Instanz ohne Verwendung der XML-deserialisierungsapis direkt aus einer Datenbank aufgefüllt wird.

### <a name="extend-the-list-of-allowed-types"></a>Erweitern der Liste der zulässigen Typen

Eine APP kann die Liste der zulässigen Typen erweitern und zusätzlich zu den oben aufgeführten integrierten Typen auch benutzerdefinierte Typen einschließen. Wenn Sie die Liste der zulässigen Typen erweitern, wirkt sich die Änderung auf _alle_ `DataSet` -und- `DataTable` Instanzen innerhalb der APP aus. Typen können nicht aus der Liste der integrierten Typen entfernt werden.

#### <a name="extend-through-configuration-net-framework-40---48"></a>Erweiterung durch Konfiguration (.NET Framework 4,0-4,8)

_App.config_ kann verwendet werden, um die Liste der zulässigen Typen zu erweitern. So erweitern Sie die Liste der zulässigen Typen:

* Verwenden Sie das- `<configSections>` Element, um einen Verweis auf den _System. Data_ -Konfigurations Abschnitt hinzuzufügen.
* Verwenden `<system.data.dataset.serialization>` / `<allowedTypes>` Sie, um zusätzliche Typen anzugeben.

Jedes `<add>` Element muss mithilfe seines qualifizierten Assemblynamens nur einen Typ angeben. Verwenden Sie mehrere-Elemente, um der Liste der zulässigen Typen weitere Typen hinzuzufügen `<add>` .

Im folgenden Beispiel wird gezeigt, wie die Liste der zulässigen Typen durch Hinzufügen des benutzerdefinierten Typs erweitert wird `Fabrikam.CustomType` .

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add type="assembly qualified type name" /> -->
      <add type="Fabrikam.CustomType, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
      <!-- additional <add /> elements as needed -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

Verwenden Sie zum Abrufen des qualifizierten [Assemblynamens eines Typs die Type. AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) -Eigenschaft, wie im folgenden Code gezeigt.

```csharp
string assemblyQualifiedName = typeof(Fabrikam.CustomType).AssemblyQualifiedName;
```

<a name="etc"></a>

#### <a name="extend-through-configuration-net-framework-20---35"></a>Erweiterung durch Konfiguration (.NET Framework 2,0-3,5)

Wenn Ihre APP auf .NET Framework 2,0 oder 3,5 ausgerichtet ist, können Sie weiterhin den oben genannten _App.config_ Mechanismus verwenden, um die Liste der zulässigen Typen zu erweitern. `<configSections>`Das-Element sieht jedoch etwas anders aus, wie im folgenden Code gezeigt:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- The below <sectionGroup> and <section> are specific to .NET Framework 2.0 and 3.5. -->
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add /> elements, as demonstrated in the .NET Framework 4.0 - 4.8 sample code above. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

#### <a name="extend-programmatically-net-framework-net-core-net-50"></a>Programm gesteuertes erweitern (.NET Framework, .net Core, .net 5.0 und höher)

Die Liste der zulässigen Typen kann auch Programm gesteuert erweitert werden, indem " [AppDomain. SetData](/dotnet/api/system.appdomain.setdata) " mit dem bekannten Schlüssel _System. Data. datasetdefaultallowedtypes_verwendet wird, wie im folgenden Code gezeigt.

```csharp
Type[] extraAllowedTypes = new Type[]
{
    typeof(Fabrikam.CustomType),
    typeof(Contoso.AdditionalCustomType)
};

AppDomain.CurrentDomain.SetData("System.Data.DataSetDefaultAllowedTypes", extraAllowedTypes);
```

Wenn Sie den Erweiterungsmechanismus verwenden, muss der Wert, der dem Schlüssel _System. Data. datasetdefaultallowedtypes_ zugeordnet ist, vom Typ sein `Type[]` .

Auf .NET Framework kann die Liste der zulässigen Typen mit _App.config_ und erweitert werden `AppDomain.SetData` . In diesem Fall `DataSet` können und `DataTable` ein Objekt als Teil der Daten deserialisiert werden, wenn der Typ in einer der beiden Listen vorhanden ist.

### <a name="run-an-app-in-audit-mode-net-framework"></a>Ausführen einer APP im Überwachungsmodus (.NET Framework)

In .NET Framework werden `DataSet` und `DataTable` eine Funktion für den Überwachungsmodus bereitstellen. Wenn der Überwachungsmodus aktiviert ist, `DataSet` und `DataTable` vergleichen Sie die Typen eingehender Objekte mit der Liste der zulässigen Typen. Wenn jedoch ein Objekt, dessen Typ nicht zulässig ist, angezeigt wird, wird **keine** Ausnahme ausgelöst. `DataSet`Und `DataTable` Benachrichtigen alle angefügten `TraceListener` Instanzen, dass ein Verdächtiger Typ vorhanden ist, sodass `TraceListener` diese Informationen protokolliert werden können. Es wird keine Ausnahme ausgelöst, und der Deserialisierungsvorgang wird fortgesetzt.

> [!WARNING]
> Das Ausführen einer APP im Überwachungsmodus sollte nur ein temporäres Measure sein, das zum Testen verwendet wird. Wenn der Überwachungsmodus aktiviert ist `DataSet` , `DataTable` erzwingen und erzwingen keine Typeinschränkungen, wodurch eine Sicherheitslücke in der APP eingeführt werden kann. Weitere Informationen finden Sie in den Abschnitten [Entfernen aller Typeinschränkungen](#ratr) und [Sicherheit in Bezug auf nicht vertrauenswürdige Eingaben](#swr).

Der Überwachungsmodus kann über _App.config_aktiviert werden:

* Weitere Informationen über den richtigen Wert für das-Element finden Sie im Abschnitt [Erweitern der Konfiguration](#etc) in diesem Dokument `<configSections>` .
* Verwenden `<allowedTypes auditOnly="true">` Sie, um den Überwachungsmodus zu aktivieren, wie im folgenden Markup gezeigt.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- See the section of this document titled "Extending through configuration" for the appropriate
         <sectionGroup> and <section> elements to put here, depending on whether you're running .NET
         Framework 2.0 - 3.5 or 4.0 - 4.8. -->
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes auditOnly="true"> <!-- setting auditOnly="true" enables audit mode -->
      <!-- Optional <add /> elements as needed. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

Sobald der Überwachungsmodus aktiviert ist, können Sie _App.config_ verwenden, um eine Verbindung mit `TraceListener` dem `DataSet` integrierten `TraceSource.` Namen der integrierten Ablauf Verfolgungs Quelle herzustellen. _System.Data.DataSet_ Im folgenden Beispiel wird veranschaulicht, wie Ablauf Verfolgungs Ereignisse in die Konsole _und_ in eine Protokolldatei auf dem Datenträger geschrieben werden.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.Data.DataSet"
              switchType="System.Diagnostics.SourceSwitch"
              switchValue="Warning">
        <listeners>
          <!-- write to the console -->
          <add name="console"
               type="System.Diagnostics.ConsoleTraceListener" />
          <!-- *and* write to a log file on disk -->
          <add name="filelog"
               type="System.Diagnostics.TextWriterTraceListener"
               initializeData="c:\logs\mylog.txt" />
        </listeners>
      </source>
    </sources>
  </system.diagnostics>
</configuration>
```

Weitere Informationen zu `TraceSource` und `TraceListener` finden Sie im Dokument Gewusst [wie: Verwenden von TraceSource und Filtern mit](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md)Ablaufverfolgungslistenern.

> [!NOTE]
> Das Ausführen einer APP im Überwachungsmodus ist in .net Core oder .net 5,0 und höher nicht verfügbar.

<a name="ratr"></a>

### <a name="remove-all-type-restrictions"></a>Alle Typeinschränkungen entfernen

Wenn eine APP alle typeinschränkungs Einschränkungen von und entfernen muss `DataSet` `DataTable` :

* Es gibt mehrere Optionen, um typeinschränkungs Beschränkungen zu unterdrücken.
* Welche Optionen verfügbar sind, hängt vom Framework ab, auf das die APP abzielt.

> [!WARNING]
> Wenn alle Typeinschränkungen entfernt werden, kann dies zu einer Sicherheitslücke in der APP führen. Wenn Sie diesen Mechanismus verwenden, stellen Sie sicher, dass die APP **nicht** `DataSet` oder `DataTable` zum Lesen nicht vertrauenswürdiger Eingaben verwendet. Weitere Informationen finden Sie unter [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) und im folgenden Abschnitt mit dem Titel [Sicherheit in Bezug auf nicht vertrauenswürdige Eingaben](#swr).

#### <a name="through-appcontext-configuration-net-framework-46---48-net-core-21-and-later-net-50-and-later"></a>Über appContext-Konfiguration (.NET Framework 4,6-4,8, .net Core 2,1 und höher, .net 5,0 und höher)

`AppContext`Wenn der Schalter `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` auf festgelegt ist, werden `true` alle typeinschränkungs Einschränkungen von `DataSet` und entfernt `DataTable` .

In .NET Framework kann dieser Schalter über _App.config_aktiviert werden, wie in der folgenden Konfiguration gezeigt:

```xml
<configuration>
   <runtime>
      <!-- Warning: setting the following switch can introduce a security problem. -->
      <AppContextSwitchOverrides value="Switch.System.Data.AllowArbitraryDataSetTypeInstantiation=true" />
   </runtime>
</configuration>
```

In ASP.net ist das- `<AppContextSwitchOverrides>` Element nicht verfügbar. Stattdessen kann der Schalter über _Web.config_aktiviert werden, wie in der folgenden Konfiguration gezeigt:

```xml
<configuration>
    <appSettings>
        <!-- Warning: setting the following switch can introduce a security problem. -->
        <add key="AppContext.SetSwitch:Switch.System.Data.AllowArbitraryDataSetTypeInstantiation" value="true" />
    </appSettings>
</configuration>
```

Weitere Informationen finden Sie unter dem- [\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) Element.

In .net Core, .net 5 und ASP.net Core wird diese Einstellung durch _runtimeconfig.jsauf_gesteuert, wie im folgenden JSON-Code gezeigt:

```json
{
  "runtimeOptions": {
    "configProperties": {
      "Switch.System.Data.AllowArbitraryDataSetTypeInstantiation": true
    }
  }
}
```

Weitere Informationen finden Sie unter ["Einstellungen für die .net Core-Laufzeitkonfiguration"](../../../../core/run-time-config/index.md).

`AllowArbitraryDataSetTypeInstantiation` kann auch Programm gesteuert über [appContext. sezwitch](/dotnet/api/system.appcontext.setswitch) festgelegt werden, anstatt eine Konfigurationsdatei zu verwenden, wie im folgenden Code gezeigt:

```csharp
// Warning: setting the following switch can introduce a security problem.
AppContext.SetSwitch("Switch.System.Data.AllowArbitraryDataSetTypeInstantiation", true);
```

 Wenn Sie den vorhergehenden programmgesteuerten Ansatz auswählen, sollte der-Aufrufvorgang `AppContext.SetSwitch` früh beim Starten der app auftreten.

#### <a name="through-the-machine-wide-registry-net-framework-20---48"></a>Über die Computer weite Registrierung (.NET Framework 2,0-4,8)

Wenn `AppContext` nicht verfügbar ist, können typeinschränkungs Überprüfungen mit der Windows-Registrierung deaktiviert werden:

* Ein Administrator muss die Registrierung konfigurieren.
* Die Verwendung der Registrierung ist eine Computer weite Änderung und wirkt sich auf _alle_ Apps aus, die auf dem Computer ausgeführt werden.

| Typ  |  Wert |
|---|---|
| **Registrierungsschlüssel** | `HKLM\SOFTWARE\Microsoft\.NETFramework\AppContext` |
| **Wertname** | `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` |
| **Werttyp** | `REG_SZ` |
| **Wertdaten** | `true` |

Bei einem 64-Bit-Betriebssystem muss dieser Wert, der sowohl für den 64-Bit-Schlüssel (oben gezeigt) als auch für den 32-Bit-Schlüssel hinzugefügt werden muss, hinzugefügt werden. Der 32-Bit-Schlüssel befindet sich unter `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext` .

Weitere Informationen zum Verwenden der Registrierung zum Konfigurieren von `AppContext` finden Sie unter ["appContext für Bibliotheksconsumer"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).

<a name="swr"></a>

## <a name="safety-with-regard-to-untrusted-input"></a>Sicherheit in Bezug auf nicht vertrauenswürdige Eingaben

Während `DataSet` und `DataTable` erzwingen Standardbeschränkungen für die Typen, die während der Deserialisierung von XML-Nutzlasten vorhanden sein dürfen, __ `DataSet` und `DataTable` sind im Allgemeinen nicht sicher, wenn Sie mit nicht vertrauenswürdiger Eingabe__ aufgefüllt werden. Im folgenden finden Sie eine nicht vollständige Liste der Methoden, mit denen eine- `DataSet` oder- `DataTable` Instanz möglicherweise nicht vertrauenswürdige Eingaben liest.

* Ein `DataAdapter` verweist auf eine-Datenbank, und die- `DataAdapter.Fill` Methode wird verwendet, um eine `DataSet` mit dem Inhalt einer Datenbankabfrage aufzufüllen.
* Die `DataSet.ReadXml` -Methode oder die- `DataTable.ReadXml` Methode wird zum Lesen einer XML-Datei mit Spalten-und Zeilen Informationen verwendet.
* Eine- `DataSet` oder- `DataTable` Instanz wird als Teil eines ASP.net (SOAP)-Webdiensts oder eines WCF-Endpunkts serialisiert.
* Ein Serialisierungsprogramm wie `XmlSerializer` wird verwendet, um eine- `DataSet` Instanz oder eine- `DataTable` Instanz aus einem XML-Stream zu deserialisieren.
* Ein Serialisierungsprogramm wie `JsonConvert` wird verwendet, um eine- `DataSet` Instanz oder eine- `DataTable` Instanz aus einem JSON-Stream zu deserialisieren. `JsonConvert` ist eine Methode im beliebten Drittanbieter- [Newtonsoft.Jsfür](https://www.newtonsoft.com/json) die-Bibliothek.
* Ein Serialisierungsprogramm wie `BinaryFormatter` wird zum Deserialisieren einer- `DataSet` oder- `DataTable` Instanz aus einem Rohdaten Strom verwendet.

In diesem Dokument werden die Sicherheitsüberlegungen für die vorangegangenen Szenarien erläutert.

## <a name="use-dataadapterfill-to-populate-a-dataset-from-an-untrusted-data-source"></a>Verwenden `DataAdapter.Fill` zum Auffüllen eines `DataSet` aus einer nicht vertrauenswürdigen Datenquelle

Eine- `DataSet` Instanz kann mithilfe der-Methode aus einem ausgefüllt werden `DataAdapter` , wie im folgenden Beispiel gezeigt. [ `DataAdapter.Fill` ](/dotnet/api/system.data.common.dataadapter.fill)

```csharp
// Assumes that connection is a valid SqlConnection object.
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);

DataSet customers = new DataSet();
adapter.Fill(customers, "Customers");
```

(Das obige Codebeispiel ist Teil eines größeren Beispiels, das beim Auffüllen [eines Datasets von einem DataAdapter](../populating-a-dataset-from-a-dataadapter.md)-Element enthalten ist.)

> Die meisten apps können vereinfachen und davon ausgehen, dass Ihre Datenbankebene vertrauenswürdig ist. Wenn Sie jedoch eine [Bedrohungsmodellierung](https://www.microsoft.com/securityengineering/sdl/threatmodeling) für Ihre apps durchlaufen, kann Ihr Bedrohungs Modell davon abweichen, dass es eine Vertrauens Grenze zwischen der Anwendung (Client) und der Datenbankschicht (Server) gibt. Die Verwendung der [gegenseitigen Authentifizierung](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) oder der [Aad-Authentifizierung](/azure/azure-sql/database/authentication-aad-overview) zwischen Client und Server ist eine Möglichkeit, um die Risiken zu beheben, die mit diesem verbunden sind. Im restlichen Teil dieses Abschnitts wird das mögliche Ergebnis eines Clients erläutert, der eine Verbindung mit einem nicht vertrauenswürdigen Server herstellt.

Die Auswirkungen, die auf eine `DataAdapter` nicht vertrauenswürdige Datenquelle verweisen, hängen von der Implementierung der `DataAdapter` selbst ab.

### <a name="sqldataadapter"></a>SqlDataAdapter

Für den integrierten Typ [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter)könnte das verweisen auf eine nicht vertrauenswürdige Datenquelle zu einem Denial-of-Service-Angriff (DOS) führen. Der DOS-Angriff könnte dazu führen, dass die APP nicht mehr reagiert oder abgestürzt wird. Wenn ein Angreifer eine DLL neben der APP zusammenstellen kann, kann er möglicherweise auch eine lokale Codeausführung erreichen.

### <a name="other-dataadapter-types"></a>Andere DataAdapter-Typen

`DataAdapter`Implementierungen von Drittanbietern müssen eigene Bewertungen darüber treffen, welche Sicherheitsgarantien Sie bei nicht vertrauenswürdigen Eingaben bereitstellen. .Net kann für diese Implementierungen keinerlei Sicherheitsgarantien treffen.

<a name="dsrdtr"></a>

## <a name="datasetreadxml-and-datatablereadxml"></a>DataSet. Read XML und databel. Read XML

Die `DataSet.ReadXml` -Methode und die- `DataTable.ReadXml` Methode sind bei Verwendung mit nicht vertrauenswürdigen Eingaben nicht sicher. Es wird dringend empfohlen, dass Consumer stattdessen eine der alternativen verwenden, die weiter unten in diesem Dokument beschrieben werden.

Die Implementierungen von `DataSet.ReadXml` und `DataTable.ReadXml` wurden ursprünglich erstellt, bevor die Sicherheitsrisiken der Serialisierung eine gut verständliche Bedrohungs Kategorie waren. Folglich befolgt der Code die aktuellen bewährten Sicherheitsmethoden nicht. Diese APIs können als Vektoren für Angreifer verwendet werden, um DOS-Angriffe auf Web-Apps auszuführen. Diese Angriffe können dazu führen, dass der Webdienst nicht reagiert oder zu unerwartetem Prozess Abbruch führt. Das Framework bietet keine entschärfungen für diese Angriffs Kategorien, und .net betrachtet dieses Verhalten "Entwurfs bedingt".

.Net hat Sicherheitsupdates veröffentlicht, um einige Probleme zu beheben, wie z. b. Offenlegung von Informationen oder Remote Codeausführung in `DataSet.ReadXml` und `DataTable.ReadXml` . Die .net-Sicherheitsupdates bieten möglicherweise keinen umfassenden Schutz gegen diese Bedrohungs Kategorien. Benutzer sollten ihre individuellen Szenarios bewerten und die potenzielle Gefahr berücksichtigen, die für sie von diesen Risiken ausgeht.

Consumer sollten beachten, dass sich Sicherheitsupdates für diese APIs in einigen Situationen auf die Anwendungs Kompatibilität auswirken können. Außerdem besteht die Möglichkeit, dass eine neue Sicherheitslücke in diesen APIs erkannt wird, für die .net nicht praktisch ein Sicherheitsupdate veröffentlichen kann.

Es wird empfohlen, dass die folgenden APIs für Consumer der folgenden APIs:

* Sie sollten eine der alternativen verwenden, die weiter unten in diesem Dokument beschrieben werden.
* Führen Sie einzelne Risikobewertungen für Ihre apps durch.

Es ist die alleinige Verantwortung des Consumers, zu bestimmen, ob diese APIs verwendet werden sollen. Consumer sollten alle Sicherheits-, technischen und rechtlichen Risiken, einschließlich gesetzlicher Anforderungen, bewerten, die möglicherweise mit diesen APIs einhergehen.

## <a name="dataset-and-datatable-via-aspnet-web-services-or-wcf"></a>DataSet und Datentabelle über ASP.NET-Webdienste oder WCF

Es ist möglich, eine- `DataSet` oder eine- `DataTable` Instanz in einem ASP.net (SOAP)-Webdienst zu akzeptieren, wie im folgenden Code gezeigt:

```csharp
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(DataTable dataTable)
    {
        /* Web method implementation. */
    }
}
```

Eine Variation hierfür besteht nicht darin, `DataSet` oder `DataTable` direkt als Parameter zu akzeptieren, sondern stattdessen als Teil des gesamten SOAP-serialisierten Objekt Diagramms zu akzeptieren, wie im folgenden Code gezeigt:

```csharp
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(MyClass data)
    {
        /* Web method implementation. */
    }
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

Oder verwenden Sie WCF anstelle von ASP.NET-Webdiensten:

```csharp
using System.Data;
using System.ServiceModel;

[ServiceContract(Namespace = "http://contoso.com/")]
public interface IMyContract
{
    [OperationContract]
    string MyMethod(DataTable dataTable);
    [OperationContract]
    string MyOtherMethod(MyClass data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

In all diesen Fällen sind das Bedrohungs Modell und die Sicherheitsgarantien mit dem [Abschnitt DataSet. Read XML und datbare. Read XML](#dsrdtr)identisch.

## <a name="deserialize-a-dataset-or-datatable-via-xmlserializer"></a>Deserialisieren eines Datasets oder einer Datentabelle über XmlSerializer

Entwickler können verwenden, `XmlSerializer` um `DataSet` -und-Instanzen zu deserialisieren `DataTable` , wie im folgenden Code gezeigt:

```csharp
using System.Data;
using System.IO;
using System.Xml.Serialization;

public DataSet PerformDeserialization1(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(DataSet));
    return (DataSet)serializer.Deserialize(stream);
}

public MyClass PerformDeserialization2(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(MyClass));
    return (MyClass)serializer.Deserialize(stream);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

In diesen Fällen sind das Bedrohungs Modell und die Sicherheitsgarantien mit dem [Abschnitt "DataSet. Read XML" und "datbare. Read XML](#dsrdtr) " identisch.

## <a name="deserialize-a-dataset-or-datatable-via-jsonconvert"></a>Deserialisieren eines Datasets oder einer Datentabelle über JsonConvert

Die beliebte newtonsoft [-Bibliothek von](https://www.newtonsoft.com/json) Drittanbietern kann verwendet werden `DataSet` , um-und-Instanzen zu deserialisieren `DataTable` , wie im folgenden Code gezeigt:

```csharp
using System.Data;
using Newtonsoft.Json;

public DataSet PerformDeserialization1(string json) {
    return JsonConvert.DeserializeObect<DataSet>(data);
}

public MyClass PerformDeserialization2(string json) {
    return JsonConvert.DeserializeObect<MyClass>(data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

Das Deserialisieren `DataSet` `DataTable` von oder auf diese Weise aus einem nicht vertrauenswürdigen JSON-BLOB ist nicht sicher. Dieses Muster ist anfällig für einen Denial-of-Service-Angriff. Ein solcher Angriff könnte die APP abstürzen oder nicht mehr reagiert.

> [!NOTE]
> Die Implementierung von Bibliotheken von Drittanbietern, wie z. b. _Newtonsoft.Js_, wird von Microsoft nicht garantiert oder unterstützt. Diese Informationen werden aus Gründen der Vollständigkeit bereitgestellt und sind zum Zeitpunkt der Erstellung dieses Artikels genau.

## <a name="deserialize-a-dataset-or-datatable-via-binaryformatter"></a>Deserialisieren eines Datasets oder einer Datentabelle über BinaryFormatter

Entwickler dürfen niemals `BinaryFormatter` , `NetDataContractSerializer` , `SoapFormatter` oder verwandte ***unsichere*** Formatierer verwenden, um eine-oder- `DataSet` `DataTable` Instanz aus einer nicht vertrauenswürdigen Nutzlast zu deserialisieren:

* Dies ist anfällig für einen vollständigen Remote Code Ausführungs Angriff.
* Die Verwendung eines benutzerdefinierten `SerializationBinder` ist nicht ausreichend, um solche Angriffe zu verhindern.

## <a name="safe-replacements"></a>Sichere Ersetzung

Für apps, die Folgendes ausführen:

* Akzeptieren Sie `DataSet` oder `DataTable` über einen ASMX-SOAP-Endpunkt oder einen WCF-Endpunkt.
* Deserialisieren nicht vertrauenswürdiger Daten in eine Instanz von `DataSet` oder `DataTable` .

Ersetzen Sie ggf. das Objektmodell, um [Entity Framework](/ef)zu verwenden. Entity Framework:

* Ist ein Funktions Reiches, modernes, objektorientiertes Framework, das relationale Daten darstellen kann.
* Bietet [ein vielfältige Ökosystem](/ef/core/providers/) von Datenbankanbietern, damit Sie Datenbankabfragen über Ihre Entity Framework-Objekt Modelle problemlos projizieren können.
* Bietet integrierte Schutzmaßnahmen beim Deserialisieren von Daten aus nicht vertrauenswürdigen Quellen.

Für apps, die `.aspx` SOAP-Endpunkte verwenden, sollten Sie diese Endpunkte für die Verwendung von [WCF](../../../wcf/index.md)ändern. WCF ist ein vollständig erstellteren Austausch für `.asmx` Webdienste. WCF-Endpunkte [können über SOAP](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) zur Kompatibilität mit vorhandenen Aufrufern verfügbar gemacht werden.

## <a name="code-analyzers"></a>Codeanalysetools

Code Analyzer-Sicherheitsregeln, die bei der Kompilierung Ihres Quellcodes ausgeführt werden, können dazu beitragen, Sicherheitsrisiken in Bezug auf dieses Sicherheitsproblem in c# und Visual Basic Code zu finden. Microsoft. Code Analysis. fxcopanalyzers ist ein nuget-Paket mit Code Analyzern, das auf [nuget.org](https://www.nuget.org/)verteilt ist.

Eine Übersicht über die Code Analysetools finden Sie unter Übersicht über die [Quellcode-Analysen](/visualstudio/code-quality/roslyn-analyzers-overview).

Aktivieren Sie die folgenden Microsoft. Code Analysis. fxcopanalyzers-Regeln:

- [CA2350](/visualstudio/code-quality/ca2350): keine Datentabelle. Read XML () mit nicht vertrauenswürdigen Daten verwenden
- [CA2351](/visualstudio/code-quality/ca2351): Verwenden Sie "DataSet. Read XML ()" nicht mit nicht vertrauenswürdigen Daten.
- [CA2352](/visualstudio/code-quality/ca2352): ein unsicheres DataSet oder eine Datentabelle in einem serialisierbaren Typ kann anfällig für Remote Code Ausführungs Angriffe sein.
- [CA2353](/visualstudio/code-quality/ca2353): unsicheres DataSet oder Datentabelle in serialisierbarem Typ
- [CA2354](/visualstudio/code-quality/ca2354): ein unsicheres DataSet oder eine Datentabelle im deserialisierten Objekt Diagramm kann für Angriffe durch Remote Codeausführung anfällig sein.
- [CA2355](/visualstudio/code-quality/ca2355): unsicheres DataSet oder Datentyp in deserialisierbarem Objekt Diagramm gefunden.
- [CA2356](/visualstudio/code-quality/ca2356): unsicheres DataSet oder Datentypen im webdeserialisierbaren Objekt Diagramm
- [CA2361](/visualstudio/code-quality/ca2361): Stellen Sie sicher, dass automatisch generierte Klassen mit DataSet. Read XML () nicht mit nicht vertrauenswürdigen Daten verwendet werden.
- [CA2362](/visualstudio/code-quality/ca2362): das unsichere DataSet oder die Datentabelle in einem automatisch generierten serialisierbaren Typ kann anfällig für Remote Code Ausführungs Angriffe sein.

Weitere Informationen zum Konfigurieren von Regeln finden Sie unter [Verwenden von Code Analyse](/visualstudio/code-quality/use-roslyn-analyzers)Modulen.

Die neuen Sicherheitsregeln sind in den folgenden nuget-Paketen verfügbar:

- Microsoft. Code Analysis. fxcopanalyzers 3.3.0: für Visual Studio 2019, Version 16,3 oder höher
- Microsoft. Code Analysis. fxcopanalyzers 2.9.11: für Visual Studio 2017, Version 15,9 oder höher
