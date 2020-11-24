---
title: ServiceModel Metadata Utility-Tool (Svcutil.exe)
description: Erfahren Sie mehr über das Service Model Metadata Utility, das den WFC-Dienstmodell Code aus Metadatendokumenten und Metadatendokumenten aus dem Dienstmodell Code generiert.
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], building
- endpoints [WCF]
- Svcutil.exe
- clients [WCF], consuming services
ms.assetid: 1abf3d9f-b420-46f1-b628-df238751f308
ms.openlocfilehash: 65013f43aa0075b6de6999741afb448c2a35afb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689926"
---
# <a name="servicemodel-metadata-utility-tool-svcutilexe"></a>ServiceModel Metadata Utility-Tool (Svcutil.exe)

Das Service Model Metadata Utility-Tool wird verwendet, um Dienstmodell Code aus Metadatendokumenten und Metadatendokumenten aus dem Dienstmodell Code zu generieren.

## <a name="svcutilexe"></a>SvcUtil.exe

Das Service Model Metadata Utility-Tool befindet sich am Windows SDK-Installations Speicherort, insbesondere *%ProgramFiles%\Microsoft SDKs\Windows\v6.0\Bin*.

### <a name="functionalities"></a>Funktionen

In der folgenden Tabelle werden die verschiedenen von diesem Tool bereitgestellten Funktionen zusammengefasst und das entsprechende Thema erläutert, in dem erläutert wird, wie es verwendet wird:

|Aufgabe|Thema|
|----------|-----------|
|Generiert Code von ausführenden Diensten oder statischen Metadatendokumenten.|[Generieren eines WCF-Clients aus Dienstmetadaten](./feature-details/generating-a-wcf-client-from-service-metadata.md)|
|Exportiert Metadatendokumente aus kompiliertem Code.|[Vorgehensweise: Verwenden von „Svcutil.exe“ zum Exportieren von Metadaten aus kompiliertem Dienstcode](./feature-details/how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md)|
|Überprüft kompilierten Dienstcode.|[Vorgehensweise: Verwenden von „Svcutil.exe“ zum Überprüfen von kompiliertem Dienstcode](./feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)|
|Lädt Metadatendokumente aus Diensten herunter, die zurzeit ausgeführt werden.|[Vorgehensweise: Verwenden von „Svcutil.exe“ zum Herunterladen von Metadatendokumenten](./feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)|
|Generiert Serialisierungscode.|[Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)|

> [!CAUTION]
> Svcutil überschreibt vorhandene Dateien auf einem Datenträger, wenn die als Parameter angegebenen Namen identisch sind. Dies kann Code Dateien, Konfigurations-oder Metadatendateien einschließen. Um dies beim Erstellen von Code-und Konfigurationsdateien zu vermeiden, verwenden Sie den- `/mergeConfig` Schalter.
>
> Außerdem dienen die `/r` Schalter und `/ct` für Verweis Typen zum Erstellen von Daten Verträgen. Diese Schalter funktionieren nicht, wenn Sie XmlSerializer verwenden.

### <a name="timeout"></a>Timeout

Das Tool hat beim Abrufen von Metadaten ein Timeout von fünf Minuten. Dieses Timeout gilt nur beim Abrufen von Metadaten über das Netzwerk. Es gilt nicht für die Verarbeitung dieser Metadaten.

### <a name="multi-targeting"></a>Festlegung von Zielversionen

Das Tool unterstützt die Festlegung von Zielversionen nicht. Wenn Sie ein .NET Framework 4-Element aus *svcutil.exe* generieren möchten, verwenden Sie die *svcutil.exe* aus dem SDK für .NET Framework 4. Verwenden Sie die ausführbare Datei aus dem .NET Framework 3,5 SDK, um ein .NET Framework 3,5-artefaktelement zu generieren.

### <a name="accessing-wsdl-documents"></a>Zugreifen auf WSDL-Dokumente

Wenn Sie mit Svcutil auf ein WSDL-Dokument zugreifen, das einen Verweis auf einen Sicherheitstokendienst (STS) enthält, führt Svcutil einen WS-MetadataExchange-Aufruf zu STS aus. Der Dienst kann jedoch seine WSDL-Dokumente entweder mithilfe von WS-MetadataExchange oder mithilfe von HTTP GET verfügbar machen. Wenn der STS das WSDL-Dokument nur mithilfe von HTTP GET verfügbar gemacht hat, schlägt ein in WinFX geschriebener Client fehl. Bei Clients, die in .NET Framework 3,5 geschrieben wurden, versucht Svcutil, sowohl WS-MetadataExchange als auch HTTP Get zu verwenden, um die STS-WSDL abzurufen.

## <a name="using-svcutilexe"></a>Verwenden von SvcUtil.exe

### <a name="common-usages"></a>Allgemeine Verwendungen

In der folgenden Tabelle sind einige häufig verwendete Optionen für dieses Tool aufgeführt:

|Option|BESCHREIBUNG|
|------------|-----------------|
|/Directory\<directory>|Das Verzeichnis, in dem die Dateien erstellt werden sollen.<br /><br /> Standard: Das aktuelle Verzeichnis.<br /><br /> Kurzform: `/d`.|
|/help|Zeigt die Befehlssyntax und Optionen für das Tool an.<br /><br /> Kurzform: `/?`.|
|/noLogo|Die Copyright- und die Bannermeldung werden unterdrückt.|
|/SvcutilConfig:\<configFile>|Gibt eine benutzerdefinierte Konfigurationsdatei an, die statt der Datei App.config verwendet werden soll. Dies kann verwendet werden, um system.serviceModel-Erweiterungen zu registrieren, ohne die Konfigurationsdatei des Tools zu ändern.|
|/target:\<output type>|Gibt die Ausgabe an, die vom Tool generiert werden soll.<br /><br /> Gültige Werte sind Code, Metadaten oder xmlSerializer.<br /><br /> Kurzform: `/t`.|

### <a name="code-generation"></a>Codeerzeugung

Svcutil.exe kann Code für Dienstverträge, Clients und Datentypen aus Metadatendokumenten generieren. Diese Metadatendokumente können sich in einem permanenten Speicher befinden oder online abgerufen werden. Der Onlineabruf erfolgt gemäß dem WS-Metadata Exchange-Protokoll oder DISCO-Protokoll (weitere Informationen finden Sie im Abschnitt Metadatendownload).

Sie können das *SvcUtil.exe* Tool zum Generieren von Dienst-und Daten Verträgen auf Grundlage eines vordefinierten WSDL-Dokuments verwenden. Verwenden Sie den /serviceContract-Schalter, und geben Sie eine URL oder einen Dateipfad für den Speicherort des WSDL-Dokuments an, an dem es gefunden oder heruntergeladen werden kann. Dadurch werden die im WSDL-Dokument definierten Dienst-und Datenverträge generiert, die dann verwendet werden können, um einen-Beschwerde Dienst zu implementieren. Weitere Informationen finden Sie unter Gewusst [wie: Abrufen von Metadaten und Implementieren eines kompatiblen Dienstanbieter](./feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md).

Für einen Dienst mit einem BasicHttpContextbinding-Endpunkt generiert *Svcutil.exe* eine BasicHttpBinding, bei der das- `allowCookies` Attribut stattdessen auf festgelegt ist `true` . Die Cookies werden auf dem Server für den Kontext verwendet. Möchten Sie den Kontext auf dem Client verwalten, wenn der Dienst Cookies verwendet, so können Sie die Konfiguration manuell für die Verwendung einer Kontextbindung ändern.

> [!CAUTION]
> Svcutil.exe generiert den Client auf der Basis der vom Dienst empfangenen WSDL- oder Richtliniendatei. Der Benutzer Prinzipal Name (User Principal Name, UPN) wird generiert, indem der Benutzername " \@ " und ein voll qualifizierter Domänen Name (FQDN) verkettet werden. Für in Active Directory registrierte Benutzer ist dieses Format jedoch nicht gültig, und der vom Tool generierte UPN verursacht einen Fehler bei der Kerberos-Authentifizierung mit der Fehlermeldung "Der Anmeldeversuch ist fehlgeschlagen". Um dieses Problem zu beheben, sollten Sie die von diesem Tool generierte Clientdatei manuell reparieren.

`svcutil.exe [/t:code]  <metadataDocumentPath>* | <url>* | <epr>`

|Argument|BESCHREIBUNG|
|--------------|-----------------|
|`epr`|Der Pfad zu einer XML-Datei, die einen WS-Addressing-EndpointReference für einen Dienstendpunkt enthält, der WS-Metadata Exchange unterstützt. Weitere Informationen finden Sie im Abschnitt Metadatendownload.|
|`metadataDocumentPath`|Der Pfad zu einem Metadatendokument (*WSDL* oder *XSD*), das den Vertrag enthält, der in den Code importiert werden soll (WSDL-, XSD-, WSPolicy-oder wsmex-Datei).<br /><br /> Svcutil folgt Importen und bezieht eine Remote-URL für Metadaten ein, sofern diese angegeben wird. Wenn Metadatendateien im lokalen Dateisystem verarbeitet werden sollen, müssen Sie alle Dateien in diesem Argument angeben. Auf diese Art können Sie Svcutil in einer Buildumgebung verwenden, in der keine Netzwerkabhängigkeiten möglich sind. Sie können Platzhalter (*. xsd, \* . WSDL) für dieses Argument verwenden.|
|`url`|Die URL zu einem Dienstendpunkt, der Metadaten bereitstellt, oder zu einem Metadatendokument, das online gehostet wird. Weitere Informationen dazu, wie diese Dokumente abgerufen werden, finden Sie im Abschnitt Metadatendownload.|

|Option|BESCHREIBUNG|
|------------|-----------------|
|/async|Generiert sowohl synchrone als auch asynchrone Methodensignaturen.<br /><br /> Standard: Es werden nur synchrone Methodensignaturen generiert.<br /><br /> Kurzform: `/a`.|
|CollectionType\<type>|Gibt den Listenauflistungstyp für einen WCF-Client an.<br/><br /> Standard: der Sammlungstyp ist System. Array. <br /><br /> Kurzform: `/ct`.|
|/config:\<configFile>|Gibt den Dateinamen für die generierte Konfigurationsdatei an.<br /><br /> Standard: output.config.|
|/dataContractOnly|Generiert nur Code für Datenvertragstypen. Dienstvertragstypen werden nicht generiert.<br /><br /> Sie sollten nur lokale Metadatendateien für diese Option angeben.<br /><br /> Kurzform: `/dconly`.|
|/enableDataBinding|Implementiert die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle für alle Datenvertragstypen, um die Datenbindung zu ermöglichen.<br /><br /> Kurzform: `/edb`.|
|/excludeType:\<type>|Gibt einen vollqualifizierten oder assemblyqualifizierten Namen an, der aus den verwiesenen Vertragstypen ausgeschlossen werden soll.<br /><br /> Beim Verwenden dieses Schalters mit `/r` aus separaten DLLs wird auf den vollständigen Namen der XSD-Klasse verwiesen.<br /><br /> Kurzform: `/et`.|
|/importXmlTypes|Konfiguriert den Datenvertragsserialisierer, um Nicht-Datenvertragstypen als IXmlSerializable-Typen zu importieren.|
|/internal|Generiert Klassen, die als intern markiert sind. Standard: Generiert nur öffentliche Klassen.<br /><br /> Kurzform: `/i`.|
|/Language\<language>|Gibt die Programmiersprache an, die zur Codegenerierung verwendet werden soll. Sie sollten entweder einen in der Machine.config-Datei registrierten Sprachnamen oder den voll qualifizierten Namen einer Klasse angeben, die von erbt <xref:System.CodeDom.Compiler.CodeDomProvider> .<br /><br /> Werte: c#, cs, csharp, vb, visualbasic, c++, cpp<br /><br /> Standard: csharp<br /><br /> Kurzform: `/l`.|
|/mergeConfig|Fügt die generierte Konfiguration in eine vorhandene Datei ein, statt die vorhandene Datei zu überschreiben.|
|/messageContract|Generiert Nachrichtenvertragstypen.<br /><br /> Kurzform: `/mc`.|
|/Namespace\<string,string>|Gibt eine Zuordnung von einem WSDL- oder XML-Schema-targetNamespace zu einem CLR-Namespace an. Durch \* die Verwendung von "" für den targetNamespace werden alle targetNamespaces ohne explizite Zuordnung zu diesem CLR-Namespace zugeordnet.<br /><br /> Um zu gewährleisten, dass der Nachrichtenvertragsname nicht mit dem Vorgangsnamen in Konflikt steht, sollten Sie den Typverweis entweder mit `::` angeben oder sicherstellen, dass die Namen einmalig sind.<br /><br /> Standard: Wird vom Zielnamespace des Schemadokuments für Datenverträge abgeleitet. Der Standardnamespace wird für alle anderen generierten Typen verwendet.<br /><br /> Kurzform: `/n` **Hinweis:**  beim Erstellen von Typen, die mit XmlSerializer verwendet werden sollen, wird nur eine einzige Namespace Zuordnung unterstützt. Alle generierten Typen befinden sich entweder im Standard Namespace oder im durch "*" angegebenen Namespace.|
|/noConfig|Es werden keine Konfigurationsdateien generiert.|
|/noStdLib|Verweist nicht auf Standardbibliotheken.<br /><br /> Standard: Es wird auf Mscorlib.dll und System.servicemodel.dll verwiesen.|
|/Out\<file>|Gibt den Dateinamen für den generierten Code an.<br /><br /> Standard: Wird vom WSDL-Definitionsnamen, WSDL-Dienstnamen oder Zielnamespace eines der Schemas abgeleitet.<br /><br /> Kurzform: `/o`.|
|/Reference\<file path>|Verweist auf Typen in der angegebenen Assembly. Beim Generieren von Clients können Sie diese Option verwenden, um Assemblys anzugeben, die unter Umständen die Typen mit den zu importierenden Metadaten enthalten.<br /><br /> Sie können mit diesem Schalter keine Nachrichtenverträge oder <xref:System.Xml.Serialization.XmlSerializer>-Typen angeben.<br /><br /> Wenn auf <xref:System.DateTimeOffset> verwiesen wird, wird dieser Typ verwendet, statt einen neuen Typ zu generieren. Wenn die Anwendung mit .NET Framework 3,5 geschrieben wird, SvcUtil.exe Verweise <xref:System.DateTimeOffset> automatisch.<br /><br /> Kurzform: `/r`.|
|/serializable|Generiert mit dem Serializable-Attribut markierte Klassen.<br /><br /> Kurzform: `/s`.|
|/serviceContract|Generiert nur Code für Dienstverträge. Clientklasse und -konfiguration werden nicht generiert.<br /><br /> Kurzform: `/sc`.|
|/serializer:Auto|Automatisches auswählen des Serialisierungsprogramms. Dabei wird versucht, das datenvertragsserialisierungsprogramm zu verwenden, und der XmlSerializer wird verwendet, wenn dies fehlschlägt<br /><br /> Kurzform: `/ser`.|
|/serializer:DataContractSerializer|Generiert Datentypen, die den Datenvertragsserialisierer für die Serialisierung und die Deserialisierung verwenden.<br /><br /> Kurzform: `/ser:DataContractSerializer`.|
|/serializer:XmlSerializer|Generiert Datentypen, die <xref:System.Xml.Serialization.XmlSerializer> für die Serialisierung und die Deserialisierung verwenden.<br /><br /> Kurzform: `/ser:XmlSerializer`.|
|/targetClientVersion|Geben Sie an, auf welche Version von .NET Framework die Anwendung abzielt. Gültige Werte sind `Version30` und `Version35`. Der Standardwert ist `Version30`.<br /><br /> Kurzform: `/tcv`.<br /><br /> `Version30`: Verwenden `/tcv:Version30` Sie, wenn Sie Code für Clients erzeugen, die WinFX verwenden.<br /><br /> `Version35`: Verwenden `/tcv:Version35` Sie, wenn Sie Code für Clients erzeugen, die .NET Framework 3,5 verwenden. Wenn Sie `/tcv:Version35` mit dem Schalter `/async` verwenden, werden ereignisbasierte und rückruf-/delegatbasierte asynchrone Methoden generiert. Außerdem wird damit Unterstützung für LINQ-aktivierte DataSets und <xref:System.DateTimeOffset> aktiviert.|
|/wrapped|Steuert, ob besondere Bedingungen für Dokumente im Dokument-Literal-Stil mit eingeschlossenen Parametern verwendet werden. Verwenden Sie den Schalter **/Wrapped** mit dem [Service Model Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) , um die normale Schreibweise anzugeben.|

> [!NOTE]
> Wenn die Dienst Bindung eine der vom System bereitgestellten Bindungen ist (siehe vom [System bereitgestellte Bindungen](system-provided-bindings.md)) und die- <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> Eigenschaft entweder auf oder festgelegt ist `None` `Sign` , generiert Svcutil eine Konfigurationsdatei mithilfe des- [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) Elements anstelle des erwarteten vom System bereitgestellten Elements. Wenn der Dienst beispielsweise das `<wsHttpBinding>`-Element verwendet, für das `ProtectionLevel` auf `Sign` festgelegt ist, wird im Bindungsabschnitt der generierten Konfiguration `<customBinding>` anstatt `<wsHttpBinding>` angezeigt. Weitere Informationen zur Schutz Ebene finden Sie Untergrund Legendes zu [Schutz Ebenen](understanding-protection-level.md).

### <a name="metadata-export"></a>Metadatenexport

Svcutil.exe kann Metadaten für Dienste, Verträge und Datentypen in kompilierten Assemblys exportieren. Um Metadaten für einen Dienst zu exportieren, müssen Sie den zu exportierenden Dienst mit der `/serviceName`-Option angeben. Um alle Datenvertragstypen innerhalb einer Assembly zu exportieren, verwenden Sie die `/dataContractOnly`-Option. Standardmäßig werden die Metadaten für alle Dienstverträge in den Eingabeassemblys exportiert.

`svcutil.exe [/t:metadata] [/serviceName:<serviceConfigName>] [/dataContractOnly] <assemblyPath>*`

|Argument|BESCHREIBUNG|
|--------------|-----------------|
|`assemblyPath`|Gibt den Pfad zu einer Assembly an, die zu exportierende Dienste, Verträge oder Datenvertragstypen enthält. Sie können standardmäßige Befehlszeilenplatzhalter verwenden, um mehrere Dateien anzugeben.|

|Option|BESCHREIBUNG|
|------------|-----------------|
|Service Name\<serviceConfigName>|Gibt den Konfigurationsnamen eines Diensts an, der exportiert werden soll. Bei Verwendung dieser Option muss eine ausführbare Assembly mit einer zugeordneten Konfigurationsdatei als Eingabe übergeben werden. Svcutil.exe durchsucht alle zugeordneten Konfigurationsdateien für die Dienstkonfiguration. Wenn die Konfigurationsdateien Erweiterungstypen enthalten, müssen die Assemblys, die diese Typen enthalten, sich entweder im GAC befinden oder ausdrücklich durch die `/reference`-Option angegeben werden.|
|/Reference\<file path>|Fügt die angegebene Assembly dem Satz von Assemblys hinzu, der zum Auflösen von Typverweisen verwendet wird. Wenn Sie einen Dienst exportieren oder überprüfen, der in der Konfiguration registrierte Drittanbietererweiterungen verwendet (Verhalten, Bindungen und Bindungselemente), können Sie diese Option zum Suchen von Erweiterungsassemblys einsetzen, die sich nicht im GAC befinden.<br /><br /> Kurzform: `/r`.|
|/dataContractOnly|Funktioniert nur bei Datenvertragstypen. Dienstverträge werden nicht verarbeitet.<br /><br /> Sie sollten nur lokale Metadatendateien für diese Option angeben.<br /><br /> Kurzform: `/dconly`.|
|/excludeType:\<type>|Gibt einen vollqualifizierten oder assemblyqualifizierten Namen eines Typs an, der aus dem Export ausgeschlossen werden soll. Diese Option kann beim Exportieren von Metadaten für einen Dienst oder einen Satz von Dienstverträgen verwendet werden, um Typen aus dem Export auszuschließen. Diese Option kann nicht zusammen mit der `/dconly`-Option verwendet werden.<br /><br /> Wenn Sie eine einzelne Assembly mit mehreren Diensten vorliegen haben und jede Assembly separate Klassen mit dem gleichen XSD-Namen verwendet, sollten Sie den Dienstnamen anstatt des XSD-Klassennamens für diesen Schalter angeben.<br /><br /> XSD- oder Datenvertragstypen werden nicht unterstützt.<br /><br /> Kurzform: `/et`.|

### <a name="service-validation"></a>Dienstvalidierung

Die Validierung kann nicht zum Erkennen von Fehlern in Dienstimplementierungen verwendet werden, ohne den Dienst zu hosten. Sie müssen die `/serviceName`-Option verwenden, um den zu überprüfenden Dienst anzugeben.

`svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*`

|Argument|BESCHREIBUNG|
|--------------|-----------------|
|`assemblyPath`|Gibt den Pfad zu einer Assembly an, die zu überprüfende Diensttypen enthält. Die Assembly muss über eine zugeordnete Konfigurationsdatei verfügen, um die Dienstkonfiguration bereitzustellen. Sie können standardmäßige Befehlszeilenplatzhalter verwenden, um mehrere Assemblys anzugeben.|

|Option|BESCHREIBUNG|
|------------|-----------------|
|/validate|Überprüft eine durch die `/serviceName`-Option angegebene Dienstimplementierung. Bei Verwendung dieser Option muss eine ausführbare Assembly mit einer zugeordneten Konfigurationsdatei als Eingabe übergeben werden.<br /><br /> Kurzform: `/v`.|
|Service Name\<serviceConfigName>|Gibt den Konfigurationsnamen eines zu überprüfenden Diensts an. Svcutil.exe durchsucht alle zugeordneten Konfigurationsdateien aller Eingabeassemblys für die Dienstkonfiguration. Wenn die Konfigurationsdateien Erweiterungstypen enthalten, müssen die Assemblys, die diese Typen enthalten, sich entweder im GAC befinden oder ausdrücklich durch die `/reference`-Option angegeben werden.|
|/Reference\<file path>|Fügt die angegebene Assembly dem Satz von Assemblys hinzu, der zum Auflösen von Typverweisen verwendet wird. Wenn Sie einen Dienst exportieren oder überprüfen, der in der Konfiguration registrierte Drittanbietererweiterungen verwendet (Verhalten, Bindungen und Bindungselemente), können Sie diese Option zum Suchen von Erweiterungsassemblys einsetzen, die sich nicht im GAC befinden.<br /><br /> Kurzform: `/r`.|
|/dataContractOnly|Funktioniert nur bei Datenvertragstypen. Dienstverträge werden nicht verarbeitet.<br /><br /> Sie sollten nur lokale Metadatendateien für diese Option angeben.<br /><br /> Kurzform: `/dconly`.|
|/excludeType:\<type>|Gibt einen vollqualifizierten oder assemblyqualifizierten Namen eines Typs an, der aus der Validierung ausgeschlossen werden soll.<br /><br /> Kurzform: `/et`.|

### <a name="metadata-download"></a>Metadatendownload

Svcutil.exe kann verwendet werden, um Metadaten aus ausführenden Diensten herunterzuladen und die Metadaten in lokalen Dateien zu speichern. Um Metadaten herunterzuladen, müssen Sie die `/t:metadata`-Option angeben. Andernfalls wird Clientcode generiert. Bei HTTP- und HTTPS-URL-Schemas versucht Svcutil.exe, Metadaten mit WS-Metadata Exchange und DISCO abzurufen. Bei allen anderen URL-Schemas verwendet Svcutil.exe nur WS-Metadata Exchange.

Svcutil gibt die folgenden Metadatenanforderungen gleichzeitig aus, um Metadaten abzurufen.

- MEX (WS-Transfer)-Anforderung an die angegebene Adresse

- MEX-Anforderung an die angegebene Adresse mit angefügtem /mex

- DISCO-Anforderung (mit DiscoveryClientProtocol von ASMX) an die angegebene Adresse

Standardmäßig verwendet „Svcutil.exe“ die in der <xref:System.ServiceModel.Description.MetadataExchangeBindings>-Klasse definierten Bindungen, um MEX-Anforderungen zu stellen. Um die für WS-Metadata Exchange verwendete Bindung zu konfigurieren, müssen Sie einen Clientendpunkt in der Konfiguration definieren, der den IMetadataExchange-Vertrag verwendet. Dies kann entweder in der Konfigurationsdatei von Svcutil.exe oder in einer anderen Konfigurationsdatei, die mit der `/svcutilConfig`-Option angegeben wird, definiert werden.

`svcutil.exe /t:metadata  <url>* | <epr>`

|Argument|BESCHREIBUNG|
|--------------|-----------------|
|`url`|Die URL zu einem Dienstendpunkt, der Metadaten bereitstellt, oder zu einem Metadatendokument, das online gehostet wird.|
|`epr`|Der Pfad zu einer XML-Datei, die einen WS-Addressing-EndpointReference für einen Dienstendpunkt enthält, der WS-Metadata Exchange unterstützt.|

### <a name="xmlserializer-type-generation"></a>XmlSerializer-Typgenerierung

Dienste und Clientanwendungen, die Datentypen verwenden, die mit dem <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können, generieren und kompilieren für diese Datentypen während der Laufzeit Code, was zu einem verlangsamten Start führen kann.

> [!NOTE]
> Vorab generierter Serialisierungscode kann nur in Clientanwendungen verwendet werden und nicht in Diensten.

Svcutil.exe kann den erforderlichen C#-Serialisierungscode aus den kompilierten Assemblys für die Anwendung generieren, um damit die Startleistung für diese Anwendungen zu verbessern. Weitere Informationen finden Sie unter Vorgehens [Weise: verbessern der Startzeit von WCF-Client Anwendungen mit dem XmlSerializer](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).

> [!NOTE]
> Svcutil.exe generiert nur Code für Typen, die von Dienstverträgen, die in der Eingabeassemblys gefunden werden, verwendet werden.

`svcutil.exe /t:xmlSerializer  <assemblyPath>*`

|Argument|BESCHREIBUNG|
|--------------|-----------------|
|`assemblyPath`|Gibt den Pfad zu einer Assembly an, die Dienstvertragstypen enthält. Serialisierungstypen werden für alle serialisierbaren XML-Typen in jedem Vertrag generiert.|

|Option|BESCHREIBUNG|
|------------|-----------------|
|/Reference\<file path>|Fügt die angegebene Assembly dem Satz von Assemblys hinzu, der zum Auflösen von Typverweisen verwendet wird.<br /><br /> Kurzform: `/r`.|
|/excludeType:\<type>|Gibt einen vollqualifizierten oder assemblyqualifizierten Namen eines Typs an, der aus dem Export oder der Validierung ausgeschlossen werden soll.<br /><br /> Kurzform: `/et`.|
|/Out\<file>|Gibt den Dateinamen für den generierten Code an. Diese Option wird ignoriert, wenn mehrere Assemblys als Eingabe an das Tool übergeben werden.<br /><br /> Standard: Wird vom Assemblynamen abgeleitet.<br /><br /> Kurzform: `/o`.|
|/UseSerializerForFaults|Gibt an, dass der <xref:System.Xml.Serialization.XmlSerializer> für Lektüre und das Schreiben von Fehlern, statt des Standard-<xref:System.Runtime.Serialization.DataContractSerializer>, verwendet werden soll.|

## <a name="examples"></a>Beispiele

Der folgende Befehl generiert Clientcode von einem ausgeführten Dienst oder Onlinemetadatendokumenten.

`svcutil http://service/metadataEndpoint`

Der folgende Befehl generiert Clientcode aus lokalen Metadatendokumenten.

`svcutil *.wsdl *.xsd /language:C#`

Der folgende Befehl generiert Datenvertragstypen in Visual Basic aus lokalen Schemadokumenten.

`svcutil /dconly *.xsd /language:VB`

Der folgende Befehl lädt Metadatendokumente aus Diensten herunter, die zurzeit ausgeführt werden.

`svcutil /t:metadata http://service/metadataEndpoint`

Der folgende Befehl generiert Metadatendokumente für Dienstverträge und zugeordnete Typen in einer Assembly.

`svcutil myAssembly.dll`

Der folgende Befehl generiert Metadatendokumente für einen Dienst und alle zugeordneten Dienstvertragstypen und Datentypen in einer Assembly.

`svcutil myServiceHost.exe /serviceName:myServiceName`

Der folgende Befehl generiert Metadatendokumente für Datentypen in einer Assembly.

`svcutil myServiceHost.exe /dconly`

Der folgende Befehl überprüft Diensthosting.

`svcutil /validate /serviceName:myServiceName myServiceHost.exe`

Der folgende Befehl generiert Serialisierungstypen für <xref:System.Xml.Serialization.XmlSerializer>-Typen, die von Dienstverträgen in der Assembly verwendet werden.

`svcutil /t:xmlserializer myContractLibrary.exe`

## <a name="maximum-nametable-character-count-quota"></a>Maximale Anzahl von Nametable-Zeichen

Wenn Sie mithilfe von svcutil.exe" die Metadaten für einen Dienst generieren, wird ggf. folgende Meldung angezeigt:

Fehler: Es können keine Metadaten aus `http://localhost:8000/somesservice/mex` dem maximalen Anzahl von NameTable-Zeichen (16384) abgerufen werden, die beim Lesen von XML-Daten überschritten wurden. Die Nametable ist eine Datenstruktur, in der bei der XML-Verarbeitung gefundene Zeichenfolgen gespeichert werden - lange XML-Dokumente mit sich nicht wiederholenden Elementnamen, Attributnamen und Attributwerten können zum Überschreiten dieses Kontingents führen. Dieses Kontingent kann durch Ändern der MaxNameTableCharCount-Eigenschaft des beim Erstellen des XML-Readers verwendeten XmlDictionaryReaderQuotas-Objekts erhöht werden.

Dieser Fehler kann durch einen Dienst verursacht werden, der eine große WSDL-Datei zurückgibt, wenn Sie die Metadaten des Diensts anfordern. Das Problem ist, dass das Zeichenkontingent für das Tool "svcutil.exe" überschritten wurde. Dieser Wert wird festgelegt, um DoS (Denial-of-Service)-Angriffe zu verhindern. Sie können dieses Kontingent erhöhen, indem Sie die folgende Konfigurationsdatei für "svcutil.exe" angeben.

Die folgende Konfigurationsdatei veranschaulicht, wie die Readerkontingente für "svcutil.exe" festgelegt werden.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <system.serviceModel>
        <bindings>
            <customBinding>
                <binding name="MyBinding">
                    <textMessageEncoding>
                        <readerQuotas maxDepth="2147483647" maxStringContentLength="2147483647"
                            maxArrayLength="2147483647" maxBytesPerRead="2147483647" maxNameTableCharCount="2147483647" />
                    </textMessageEncoding>
                    <httpTransport maxReceivedMessageSize="2147483647" maxBufferSize="2147483647" />
                </binding>
            </customBinding>
        </bindings>
        <client>
            <endpoint binding="customBinding" bindingConfiguration="MyBinding"
                contract="IMetadataExchange"
                name="http" />
        </client>
    </system.serviceModel>
</configuration>
```

Erstellen Sie eine neue Datei namens "svcutil.exe.config", und kopieren Sie den XML-Beispielcode in diese Datei. Fügen Sie die Datei dann in das gleiche Verzeichnis wie "svcutil.exe" ein. Bei der nächsten Ausführung von "svcutil.exe" werden die neuen Einstellungen abgerufen.

## <a name="security-concerns"></a>Sicherheitsaspekte

Sie sollten die entsprechende Zugriffssteuerungsliste verwenden, um den Installationsordner von "Svcutil.exe", "Svcutil.config" und Dateien, auf die `/svcutilConfig` verweist, zu schützen. Dies kann verhindern, dass bösartige Erweiterungen registriert und ausgeführt werden.

Um die Gefahr zu minimieren, dass Sicherheit gefährdet ist, sollten Sie außerdem nicht vertrauenswürdige Erweiterungen hinzufügen, die Teil des Systems sind, oder nicht vertrauenswürdige Code Anbieter mit Svcutil.exe verwenden.

Und schließlich sollten Sie das Tool nicht in der mittleren Ebene Ihrer Anwendung einsetzen, da dies einen Denial-of-Service beim aktuellen Vorgang zur Folge haben kann.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [Vorgehensweise: Erstellen eines Clients](how-to-create-a-wcf-client.md)
