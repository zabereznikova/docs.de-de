---
title: Generieren eines WCF-Clients aus Dienstmetadaten
description: Entdecken Sie die verschiedenen Switches in Svcutil.exe, die verwendet werden, um WFC-Clients aus dienstmetadatendokumenten zu generieren, die auf WSDL basieren, oder eine Richtlinien Datei vom Dienst
ms.date: 03/30/2017
ms.assetid: 27f8f545-cc44-412a-b104-617e0781b803
ms.openlocfilehash: f755a092fb3596349a6878c61fe414f4e0a9f9d1
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247272"
---
# <a name="generating-a-wcf-client-from-service-metadata"></a>Generieren eines WCF-Clients aus Dienstmetadaten
In diesem Thema wird beschrieben, wie die verschiedenen Schalter in Svcutil.exe verwendet werden, um aus Metadatendokumenten Clients zu generieren.  
  
 Die Metadatendokumente können sich in einem permanenten Speicher befinden oder online abgerufen werden. Der Onlineabruf erfolgt gemäß dem WS-MetadataExchange-Protokoll oder Microsoft Discovery (DISCO)-Protokoll. Svcutil.exe gibt zum Abruf von Metadaten die folgenden Metadatenanforderungen gleichzeitig aus.  
  
- WS-MetadataExchange (MEX)-Anforderung an die angegebene Adresse  
  
- MEX-Anforderung an die angegebene Adresse mit angefügtem `/mex`  
  
- Disco-Anforderung (mit der <xref:System.Web.Services.Discovery.DiscoveryClientProtocol> von ASP.NET-Webdiensten) zur angegebenen Adresse.  
  
 Svcutil.exe generiert den Client auf der Basis der vom Dienst empfangenen WSDL (Web Services Description Language)-Datei oder Richtliniendatei. Der Benutzer Prinzipal Name (User Principal Name, UPN) wird generiert, indem der Benutzername mit "" verkettet \@ und anschließend ein voll qualifizierter Domänen Name (FQDN) hinzugefügt wird. Für Benutzer, die sich bei Active Directory registriert haben, ist dieses Format jedoch nicht gültig, und der vom Tool generierte UPN verursacht einen Fehler bei der Kerberos-Authentifizierung mit der folgenden Fehlermeldung: Fehler **beim Anmeldeversuch.** Um dieses Problem zu beheben, sollten Sie die von diesem Tool generierte Clientdatei manuell berichtigen.  
  
```console
svcutil.exe [/t:code]  <metadataDocumentPath>* | <url>* | <epr>  
```  
  
## <a name="referencing-and-sharing-types"></a>Verweisen auf Typen und Freigeben von Typen  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/Reference\<file path>**|Verweist auf Typen in der angegebenen Assembly. Beim Generieren von Clients können Sie diese Option verwenden, um Assemblys anzugeben, die unter Umständen die Typen mit den zu importierenden Metadaten enthalten.<br /><br /> Kurzform: `/r`.|  
|**/excludeType:\<type>**|Gibt einen vollqualifizierten oder assemblyqualifizierten Namen an, der aus den verwiesenen Vertragstypen ausgeschlossen werden soll.<br /><br /> Kurzform: `/et`.|  
  
## <a name="choosing-a-serializer"></a>Wählen eines Serialisierungsprogramms  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/serializer:Auto**|Wählt die Serialisierung automatisch aus. Hierbei wird das `DataContract`-Serialisierungsmodul verwendet. Wenn dieser Versuch fehlschlägt, wird `XmlSerializer` verwendet.<br /><br /> Kurzform: `/ser:Auto`.|  
|**/serializer:DataContractSerializer**|Generiert Datentypen, die das `DataContract`-Serilisierungsprogramm für die Serialisierung und die Deserialisierung verwenden.<br /><br /> Kurzform: `/ser:DataContractSerializer`.|  
|**/serializer:XmlSerializer**|Generiert Datentypen, die `XmlSerializer` für die Serialisierung und die Deserialisierung verwenden.<br /><br /> Kurzform: `/ser:XmlSerializer`.|  
|**/importXmlTypes**|Das `DataContract`-Serialisierungsprogramm wird so konfiguriert, dass Typen, die keine `DataContract`-Typen sind, als `IXmlSerializable`-Typen importiert werden.<br /><br /> Kurzform: `/ixt`.|  
|**/dataContractOnly**|Generiert nur Code für `DataContract`-Typen. `ServiceContract`-Typen werden generiert.<br /><br /> Sie sollten für diese Option nur lokale Metadatendateien angeben.<br /><br /> Kurzform: `/dconly`.|  
  
## <a name="choosing-a-language-for-the-client"></a>Auswählen einer Sprache für den Client  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/Language\<language>**|Gibt die Programmiersprache an, die zur Codegenerierung verwendet werden soll. Sie können entweder einen in der Datei Machine.config registrierten Sprachnamen oder den vollqualifizierten Namen einer Klasse angeben, der von <xref:System.CodeDom.Compiler.CodeDomProvider> abgeleitet ist.<br /><br /> Werte: c#, cs, csharp, vb, vbs, visualbasic, vbscript, javascript, c++, mc, cpp<br /><br /> Standard: csharp<br /><br /> Kurzform: `/l`.<br /><br /> Weitere Informationen finden Sie unter <xref:System.CodeDom.Compiler.CodeDomProvider>-Klasse.|  
  
## <a name="choosing-a-namespace-for-the-client"></a>Auswählen eines Namespace für den Client  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/Namespace\<string,string>**|Gibt eine Zuordnung von einem WSDL- oder XML-Schema-`targetNamespace` zu einem CLR (Common Language Runtime)-Namespace an. Durch die Verwendung eines Platzhalters (*) für `targetNamespace` werden alle `targetNamespaces` ohne eine explizite Zuordnung diesem CLR-Namespace zugeordnet.<br /><br /> Um zu gewährleisten, dass der Nachrichtenvertragsname nicht mit dem Vorgangsnamen in Konflikt steht, sollten Sie den Typverweis entweder mit zwei Doppelpunkten (`::`) angeben oder sicherstellen, dass die Namen einmalig sind.<br /><br /> Standard: Wird vom Zielnamespace des Schemadokuments für `DataContracts` abgeleitet. Der Standardnamespace wird für alle anderen generierten Typen verwendet.<br /><br /> Kurzform: `/n`.|  
  
## <a name="choosing-a-data-binding"></a>Auswählen einer Datenbindung  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/enableDataBinding**|Implementiert die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle für alle generierten `DataContract`-Typen, um die Datenbindung zu ermöglichen.<br /><br /> Kurzform: `/edb`.|  
  
## <a name="generating-configuration"></a>Generieren der Konfiguration  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/config\<configFile>**|Gibt den Dateinamen für die generierte Konfigurationsdatei an.<br /><br /> Standard: output.config.|  
|**/mergeConfig**|Fügt die generierte Konfiguration in eine vorhandene Datei ein, statt die vorhandene Datei zu überschreiben.|  
|**/noConfig**|Es werden keine Konfigurationsdateien generiert.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Metadaten](using-metadata.md)
- [Übersicht über die Metadatenarchitektur](metadata-architecture-overview.md)
