---
title: Verbindungszeichenfolgen und Konfigurationsdateien
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 37df2641-661e-407a-a3fb-7bf9540f01e8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fe56dc279471f77a3f9ae014f65faaa99a113624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="connection-strings-and-configuration-files"></a>Verbindungszeichenfolgen und Konfigurationsdateien
Das Einbetten von Verbindungszeichenfolgen in den Code Ihrer Anwendung kann zu Sicherheitslücken und Wartungsproblemen führen. Unverschlüsselte Verbindungszeichenfolgen, die in einer Anwendung Quellcode kompiliert können angezeigt werden, mithilfe der [Ildasm.exe (IL-Disassembler)](../../../../docs/framework/tools/ildasm-exe-il-disassembler.md) Tool. Hinzu kommt, dass die Anwendung neu kompiliert werden muss, wenn sich die Verbindungszeichenfolge irgendwann einmal ändert. Aus diesen Gründen empfehlen wir, Verbindungszeichenfolgen in einer Anwendungskonfigurationsdatei zu speichern.  
  
## <a name="working-with-application-configuration-files"></a>Arbeiten mit Anwendungskonfigurationsdateien  
 Anwendungskonfigurationsdateien enthalten anwendungsspezifische Einstellungen. Eine ASP.NET-Anwendung kann z. B. haben, eine oder mehrere **"Web.config"** Dateien und eine Windows-Anwendung kann eine optionale haben **"App.config"** Datei. Konfigurationsdateien haben etliche Elemente gemein, auch wenn sich der Name und der Speicherort der Konfigurationsdateien abhängig vom jeweiligen Host der Anwendung ändert.  
  
### <a name="the-connectionstrings-section"></a>Der "connectionStrings"-Abschnitt  
 Verbindungszeichenfolgen können als Schlüssel/Wert-Paare in gespeichert werden die **ConnectionStrings** Teil der **Konfiguration** Element von einer Anwendungskonfigurationsdatei. Untergeordnete Elemente enthalten **hinzufügen**, **deaktivieren**, und **entfernen**.  
  
 Das folgende Konfigurationsdateifragment zeigt das Schema und die Syntax für das Speichern einer Verbindungszeichenfolge. Die **Namen** Attribut ist ein Name, den Sie angeben, um eine Verbindungszeichenfolge eindeutig zu identifizieren, damit es zur Laufzeit abgerufen werden kann. Die **ProviderName** ist der unveränderliche Name von der .NET Framework-Datenanbieter, die in der Datei "Machine.config" registriert wurde.  
  
```xml  
<?xml version='1.0' encoding='utf-8'?>  
  <configuration>  
    <connectionStrings>  
      <clear />  
      <add name="Name"   
       providerName="System.Data.ProviderName"   
       connectionString="Valid Connection String;" />  
    </connectionStrings>  
  </configuration>  
```  
  
> [!NOTE]
>  Sie können einen Teil der Verbindungszeichenfolge in einer Konfigurationsdatei speichern und zur Vervollständigung zur Laufzeit die <xref:System.Data.Common.DbConnectionStringBuilder>-Klasse verwenden. Diese Vorgehensweise empfiehlt sich in Szenarien, in denen Ihnen die Elemente der Verbindungszeichenfolge vorab nicht bekannt sind oder wenn Sie sicherheitsrelevante Informationen nicht in einer Konfigurationsdatei speichern möchten. Weitere Informationen finden Sie unter [Verbindungszeichenfolgen-Generatoren](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
### <a name="using-external-configuration-files"></a>Verwenden externer Konfigurationsdateien  
 Externe Konfigurationsdateien sind separate Dateien, die ein aus einem einzigen Abschnitt bestehendes Fragment einer Konfigurationsdatei enthalten. Auf die externe Konfigurationsdatei wird dann von der Hauptkonfigurationsdatei verwiesen. Speichern der **ConnectionStrings** Abschnitt in einer separaten Datei eignet sich für Situationen, in denen Verbindungszeichenfolgen können bearbeitet werden, nachdem die Anwendung bereitgestellt wird. ASP.NET verhält sich z. B. standardmäßig so, dass nach Änderungen an Konfigurationsdateien eine Anwendung neu gestartet wird, wodurch Statusinformationen verloren gehen. Änderungen an einer externen Konfigurationsdatei hingegen führen nicht zum Neustart der Anwendung. Externe Konfigurationsdateien sind nicht auf ASP.NET beschränkt und können auch von Windows-Anwendungen verwendet werden. Außerdem kann der Zugriff auf externe Konfigurationsdateien auch durch Dateizugriffssicherheit und Berechtigungen eingeschränkt werden. Der Einsatz externer Konfigurationsdateien zur Laufzeit ist transparent und erfordert keine besondere Codierung.  
  
 Um die Verbindungszeichenfolgen in einer externen Konfigurationsdatei speichern möchten, erstellen Sie eine separate Datei, die nur enthält die **ConnectionStrings** Abschnitt. Nehmen Sie in diese Datei keine zusätzlichen Elemente, Abschnitte oder Attribute auf. Das folgende Beispiel zeigt die Syntax für eine externe Konfigurationsdatei.  
  
```xml  
<connectionStrings>  
  <add name="Name"   
   providerName="System.Data.ProviderName"   
   connectionString="Valid Connection String;" />  
</connectionStrings>  
```  
  
 In der Konfigurationsdatei der Anwendung, die Sie verwenden die **"configSource"** Attribut, um den voll gekennzeichneten Namen und den Speicherort der externen Datei anzugeben. Das folgende Beispiel verweist auf eine Konfigurationsdatei mit dem Namen `connections.config`.  
  
```xml  
<?xml version='1.0' encoding='utf-8'?>  
<configuration>  
    <connectionStrings configSource="connections.config"/>  
</configuration>  
```  
  
## <a name="retrieving-connection-strings-at-run-time"></a>Abrufen von Verbindungszeichenfolgen zur Laufzeit  
 Mit .NET Framework 2.0 wurden neue Klassen im <xref:System.Configuration>-Namespace eingeführt, um das Abrufen von Verbindungszeichenfolgen aus Konfigurationsdateien zur Laufzeit zu vereinfachen. Sie können programmgesteuert eine Verbindungszeichenfolge nach Namen oder Anbieternamen abrufen.  
  
> [!NOTE]
>  Die **"Machine.config"** enthält darüber hinaus eine **ConnectionStrings** Abschnitt, der von Visual Studio verwendete Verbindungszeichenfolgen enthält. Beim Abrufen von Verbindungszeichenfolgen nach dem Anbieternamen aus der **"App.config"** Datei in einer Windows-Anwendung, die Verbindungszeichenfolgen im **"Machine.config"** erhalten Sie erste geladen und dann die Einträge aus **"App.config"**. Hinzufügen von **deaktivieren** unmittelbar nach der **ConnectionStrings** Element entfernt alle geerbten Verweise aus der Datenstruktur im Arbeitsspeicher, sodass nur die Verbindungszeichenfolgen in der lokalen definiert**"App.config"** Datei betrachtet werden.  
  
### <a name="working-with-the-configuration-classes"></a>Arbeiten mit den Konfigurationsklassen  
 Ab .NET Framework 2.0 wird bei der Arbeit mit Konfigurationsdateien auf dem lokalen Computer der <xref:System.Configuration.ConfigurationManager> verwendet, der die <xref:System.Configuration.ConfigurationSettings> ersetzt. Für die Arbeit mit ASP.NET-Konfigurationsdateien kommt der <xref:System.Web.Configuration.WebConfigurationManager> zum Einsatz. Es dient zum Arbeiten mit Konfigurationsdateien auf einem Webserver, und ermöglicht den programmgesteuerten Zugriff auf Konfigurationsdateiabschnitte wie z. B. **system.web**.  
  
> [!NOTE]
>  Wenn ein Aufrufer zur Laufzeit auf Konfigurationsdateien zugreifen können soll, benötigt er Berechtigungen. Welche Berechtigungen notwendig sind, hängt von der Art der Anwendung, der Konfigurationsdatei und dem Speicherort ab. Weitere Informationen finden Sie unter [verwenden der Konfigurationsklassen](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc) und <xref:System.Web.Configuration.WebConfigurationManager> für ASP.NET-Anwendungen und <xref:System.Configuration.ConfigurationManager> für Windows-Anwendungen.  
  
 Zum Abrufen von Verbindungszeichenfolgen aus Anwendungskonfigurationsdateien können Sie die <xref:System.Configuration.ConnectionStringSettingsCollection> verwenden. Er enthält eine Auflistung von <xref:System.Configuration.ConnectionStringSettings> Objekte, von denen jede einen einzelnen Eintrag im stellt die **ConnectionStrings** Abschnitt. Ihre Eigenschaften werden entsprechenden Verbindungszeichenfolgenattributen zugeordnet, sodass es möglich ist, Verbindungszeichenfolgen nach dem Namen oder dem Anbieternamen abzurufen.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Configuration.ConnectionStringSettings.Name%2A>|Name der Verbindungszeichenfolge: Ordnet die **Namen** Attribut.|  
|<xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>|Vollqualifizierter Anbietername: Ordnet die **ProviderName** Attribut.|  
|<xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A>|Verbindungszeichenfolge. Ordnet die **"ConnectionString"** Attribut.|  
  
### <a name="example-listing-all-connection-strings"></a>Beispiel: Auflisten aller Verbindungszeichenfolgen  
 Dieses Beispiel durchläuft die `ConnectionStringSettings`-Auflistung und zeigt im Konsolenfenster die Eigenschaften <xref:System.Configuration.ConnectionStringSettings.Name%2A>, <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> und <xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A> an.  
  
> [!NOTE]
>  <legacyBold>System.Configuration.dll</legacyBold> ist nicht in allen Projekttypen enthalten, sodass Sie u. U. einen Verweis einfügen müssen, um die Konfigurationsklassen zu verwenden. Wie die jeweilige Anwendungskonfigurationsdatei heißt und wo sie gespeichert ist, hängt von der Art der Anwendung und dem Hostingprozess ab.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/VB/source.vb#1)]  
  
### <a name="example-retrieving-a-connection-string-by-name"></a>Beispiel: Abrufen einer Verbindungszeichenfolge nach dem Namen  
 In diesem Beispiel wird gezeigt, wie eine Verbindungszeichenfolge aus einer Konfigurationsdatei durch Angabe ihres Namens abgerufen werden kann. Der Code erstellt ein <xref:System.Configuration.ConnectionStringSettings>-Objekt, das den bereitgestellten Eingabeparameter mit dem <xref:System.Configuration.ConfigurationManager.ConnectionStrings%2A>-Namen abgleicht. Wird kein übereinstimmender Name gefunden, gibt die Funktion `null` (`Nothing` in Visual Basic) zurück.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/VB/source.vb#1)]  
  
### <a name="example-retrieving-a-connection-string-by-provider-name"></a>Beispiel: Abrufen einer Verbindungszeichenfolge nach dem Anbieternamen  
 In diesem Beispiel wird veranschaulicht, wie eine Verbindungszeichenfolge durch Angabe der Anbieternamens im Format *System.Data.ProviderName*. Der Code durchläuft die <xref:System.Configuration.ConnectionStringSettingsCollection> und gibt die Verbindungszeichenfolge für den ersten gefundenen <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>-Eintrag zurück. Wird kein Anbietername gefunden, gibt die Funktion `null` (`Nothing` in Visual Basic) zurück.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="encrypting-configuration-file-sections-using-protected-configuration"></a>Verschlüsseln von Konfigurationsdateiabschnitten mit geschützter Konfiguration  
 ASP.NET 2.0 eine neue Funktion eingeführt *geschützten Konfiguration*, mit der Sie sicherheitsrelevante Informationen in einer Konfigurationsdatei verschlüsseln. Die geschützte Konfiguration wurde zwar primär für ASP.NET entwickelt, sie kann aber auch zum Verschlüsseln von Konfigurationsdateiabschnitten in Windows-Anwendungen verwendet werden. Eine ausführliche Beschreibung der Funktionen die geschützte Konfiguration, finden Sie unter [Verschlüsseln von Informationen mithilfe von geschützten Konfiguration](http://msdn.microsoft.com/library/51cdfe5b-9d82-458c-94ff-c551c4f38ed1).  
  
 Das folgende Konfigurationsdateifragment zeigt die **ConnectionStrings** -Abschnitt nach verschlüsselt wurde. Die **ConfigProtectionProvider** gibt an, die geschützte Konfigurationsanbieter zum Verschlüsseln und Entschlüsseln der Verbindungszeichenfolgen verwendet. Die **EncryptedData** -Abschnitt enthält den Verschlüsselungstext.  
  
```xml  
<connectionStrings configProtectionProvider="DataProtectionConfigurationProvider">  
  <EncryptedData>  
    <CipherData>  
      <CipherValue>AQAAANCMnd8BFdERjHoAwE/Cl+sBAAAAH2... </CipherValue>  
    </CipherData>  
  </EncryptedData>  
</connectionStrings>  
```  
  
 Wenn die verschlüsselte Verbindungszeichenfolge zur Laufzeit abgerufen wird, verwendet .NET Framework den angegebenen Anbieter zum Entschlüsseln der **CipherValue** und Ihre Anwendung zur Verfügung zu stellen. Sie müssen für die Verwaltung des Entschlüsselungsprozesses keinen zusätzlichen Code schreiben.  
  
### <a name="protected-configuration-providers"></a>Anbieter für die geschützte Konfiguration  
 Geschützte Konfigurationsanbieter registriert sind, der **ConfigProtectedData** Teil der **"Machine.config"** Datei auf dem lokalen Computer, wie im folgenden Fragment gezeigt, die die beiden zeigt geschützte Konfigurationsanbieter mit .NET Framework bereitgestellt. Die hier gezeigten Werte wurden aus Gründen der besseren Lesbarkeit gekürzt.  
  
```xml  
<configProtectedData defaultProvider="RsaProtectedConfigurationProvider">  
  <providers>  
    <add name="RsaProtectedConfigurationProvider"   
      type="System.Configuration.RsaProtectedConfigurationProvider, ... />  
    <add name="DataProtectionConfigurationProvider"   
      type="System.Configuration.DpapiProtectedConfigurationProvider, ... />  
  </providers>  
</configProtectedData>  
```  
  
 Sie können zusätzliche geschützte Konfigurationsanbieter konfigurieren, indem sie zum Hinzufügen der **"Machine.config"** Datei. Sie können auch einen eigenen Anbieter für die geschützte Konfiguration erstellen, indem Sie von der abstrakten Basisklasse <xref:System.Configuration.ProtectedConfigurationProvider> erben. In der folgenden Tabelle werden die zwei in .NET Framework enthaltenen Anbieter für die geschützte Konfiguration beschrieben.  
  
|Anbieter|Beschreibung|  
|--------------|-----------------|  
|<!--zz<xref:System.Configuration.RSAProtectedConfigurationProvider>-->`System.Configuration.RSAProtectedConfigurationProvider`|Verwendet zum Verschlüsseln und Entschlüsseln der Daten den RSA-Verschlüsselungsalgorithmus. Der RSA-Algorithmus kann sowohl für die Verschlüsselung mit öffentlichem Schlüssel als auch für digitale Signaturen verwendet werden. Er wird auch als "öffentlicher Schlüssel" oder asymmetrische Verschlüsselung bezeichnet, da bei dieser Art der Verschlüsselung zwei verschiedene Schlüssel eingesetzt werden. Sie können die [ASP.NET IIS-Registrierungstool (Aspnet_regiis.exe)](http://msdn.microsoft.com/library/6491c41e-e2b0-481f-9863-db3614d5f96b) zum Verschlüsseln von Abschnitten in einer Datei "Web.config" und die Verschlüsselungsschlüssel verwalten. ASP.NET entschlüsselt die Konfigurationsdatei, wenn die Datei verarbeitet wird. Die Identität der ASP.NET-Anwendung muss berechtigt sein, den Verschlüsselungsschlüssel zu lesen, mit dem die verschlüsselten Abschnitte verschlüsselt und entschlüsselt werden.|  
|<!--zz<xref:System.Configuration.DPAPIProtectedConfigurationProvider>-->`System.Configuration.DPAPIProtectedConfigurationProvider`|Verwendet zum Verschlüsseln der Konfigurationsabschnitte die Windows-Datenschutz-API (DPAPI). Die DPAPI verwendet die in Windows integrierten Kryptografiedienste, und sie kann für den computerspezifischen oder den benutzerkontospezifischen Schutz konfiguriert werden. Der computerspezifische Schutz bietet sich an, wenn auf demselben Server mehrere Anwendungen vorhanden sind, die Informationen gemeinsam nutzen müssen. Die Verwendung des benutzerkontospezifischen Schutzes empfiehlt sich bei Diensten, die mit einer bestimmten Benutzeridentität, z. B. einer freigegebenen gehosteten Umgebung, ausgeführt werden. Jede Anwendung wird unter einer separaten Identität ausgeführt, was den Zugriff auf Ressourcen, wie z. B. Dateien und Datenbanken, einschränkt.|  
  
 Beide Anbieter bieten eine starke Verschlüsselung der Daten. Wenn Sie aber beabsichtigen, ein und dieselbe verschlüsselte Konfigurationsdatei auf mehreren Servern, z. B. in einer Webfarm, zu verwenden, müssen Sie den `RsaProtectedConfigurationProvider` verwenden, da nur er die Möglichkeit bietet, die zum Verschlüsseln der Daten verwendeten Verschlüsselungsschlüssel zu exportieren und sie auf einem anderen Server zu importieren. Weitere Informationen finden Sie unter [importieren und Exportieren von geschützten Konfiguration RSA Key Containers](http://msdn.microsoft.com/library/f3022b39-f17f-48c1-b067-025eab0ce8bc).  
  
### <a name="using-the-configuration-classes"></a>Verwenden der Konfigurationsklassen  
 Der <xref:System.Configuration>-Namespace stellt Klassen zum programmgesteuerten Arbeiten mit Konfigurationseinstellungen bereit. Die <xref:System.Configuration.ConfigurationManager>-Klasse ermöglicht den Zugriff auf Computer-, Anwendungs- und Benutzerkonfigurationsdateien. Wenn Sie eine ASP.NET-Anwendung erstellen, können Sie mithilfe der <xref:System.Web.Configuration.WebConfigurationManager> Klasse, die die gleiche Funktionalität bereitstellt, während ermöglicht es Ihnen auf Einstellungen zugreifen, die spezifisch für ASP.NET-Anwendungen, z. B. die sind außerdem in gefunden  **\< System.Web >**.  
  
> [!NOTE]
>  Der <xref:System.Security.Cryptography>-Namespace enthält Klassen, die zusätzliche Optionen zum Verschlüsseln und Entschlüsseln von Daten bereitstellen. Verwenden Sie diese Klassen, wenn Sie Kryptografiedienste benötigen, die bei Verwendung der geschützten Konfiguration nicht verfügbar sind. Einige dieser Klassen sind Wrapper für die nicht verwaltete Microsoft CryptoAPI, während es sich bei anderen Klassen um verwaltete Implementierungen handelt. Weitere Informationen finden Sie unter [Kryptografiedienste](http://msdn.microsoft.com/en-us/68a1e844-c63c-44af-9247-f6716eb23781).  
  
### <a name="appconfig-example"></a>"App.config"-Beispiel  
 In diesem Beispiel wird veranschaulicht, wie Verschlüsseln aktivieren bzw. Deaktivieren der **ConnectionStrings** im Abschnitt ein **"App.config"** Datei für eine Windows-Anwendung. In diesem Beispiel übernimmt die Prozedur den Namen der Anwendung, z. B. <legacyBold>MyApplication.exe</legacyBold>, als Argument. Die **"App.config"** -Datei wird dann verschlüsselt und in den Ordner mit der ausführbaren Datei mit dem Namen "MyApplication.exe.config" kopiert.  
  
> [!NOTE]
>  Die Verbindungszeichenfolge kann nur auf dem Computer entschlüsselt werden, auf dem sie verschlüsselt wurde.  
  
 Der Code verwendet die <xref:System.Configuration.ConfigurationManager.OpenExeConfiguration%2A> Methode zum Öffnen der **"App.config"** Datei für die Bearbeitung und <xref:System.Configuration.ConfigurationManager.GetSection%2A> Methode gibt die **ConnectionStrings** Abschnitt. Der Code überprüft nun die <xref:System.Configuration.SectionInformation.IsProtected%2A>-Eigenschaft, indem er die <xref:System.Configuration.SectionInformation.ProtectSection%2A>-Methode aufruft, um den Abschnitt zu verschlüsseln, sofern dieser nicht bereits verschlüsselt ist. Die <xref:System.Configuration.SectionInformation.UnprotectSection%2A>-Methode wird aufgerufen, um den Abschnitt zu entschlüsseln. Die <xref:System.Configuration.Configuration.Save%2A>-Methode schließt den Vorgang ab und speichert die Änderungen.  
  
> [!NOTE]
>  Sie müssen in Ihrem Projekt einen Verweis auf `System.Configuration.dll` angeben, damit der Code ausgeführt wird.  
  
 [!code-csharp[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/VB/source.vb#1)]  
  
### <a name="webconfig-example"></a>"Web.config"-Beispiel  
 Das folgende Beispiel verwendet die <xref:System.Web.Configuration.WebConfigurationManager.OpenWebConfiguration%2A>-Methode `WebConfigurationManager`. Beachten Sie, dass in diesem Fall den relativen Pfad zum standardimages können die **"Web.config"** Datei mit einer Tilde. Der Code benötigt einen Verweis auf die `System.Web.Configuration`-Klasse.  
  
 [!code-csharp[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/VB/source.vb#1)]  
  
 Weitere Informationen zum Absichern von ASP.NET-Anwendungen finden Sie unter [NIB: ASP.NET-Sicherheit](http://msdn.microsoft.com/en-us/04b37532-18d9-40b4-8e5f-ee09a70b311d) und [ASP.NET 2.0 Sicherheitsmaßnahmen auf einen Blick](http://go.microsoft.com/fwlink/?LinkId=59997) im ASP.NET Developer Center.  
  
## <a name="see-also"></a>Siehe auch  
 [Verbindungszeichenfolgen-Generatoren](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [Verwenden der Konfigurationsklassen](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc)  
 [Konfigurieren von Apps](../../../../docs/framework/configure-apps/index.md)  
 [ASP.NET Web Siteadministration](http://msdn.microsoft.com/library/1298034b-5f7d-464d-abd1-ad9e6b3eeb7e)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
