---
title: Übersicht über die Integration von COM+-Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: e481e48f-7096-40eb-9f20-7f0098412941
ms.openlocfilehash: 57a1537e1bde1efcd3586d032efee063561efcca
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586493"
---
# <a name="integrating-with-com-applications-overview"></a>Übersicht über die Integration von COM+-Anwendungen
Windows Communication Foundation (WCF) stellt eine umfangreiche Umgebung zum Erstellen verteilter Anwendungen bereit. Wenn Sie bereits komponentenbasierte Anwendungslogik verwenden, die in com+ gehostet wird, können Sie die vorhandene Logik mithilfe von WCF erweitern, anstatt Sie neu schreiben zu müssen. Ein häufiges Szenario ist das Verfügbarmachen vorhandener COM+- oder Enterprise Services-Geschäftslogik über Webdienste.  
  
 Wenn eine Schnittstelle auf einer COM+-Komponente als Webdienst verfügbar gemacht wird, werden die Spezifikation und der Vertrag dieser Dienste von einer automatischen Zuordnung bestimmt, die zur Anwendungsinitialisierungszeit ausgeführt wird. In der folgenden Liste wird das Modell für diese Zuordnung gezeigt:  
  
- Ein Dienst wird für jede verfügbar gemachte COM-Klasse definiert.  
  
- Der Vertrag für den Dienst wird direkt von der Schnittstellendefinition der ausgewählten Komponente abgeleitet, wobei die Möglichkeit des Methodenausschlusses in der Konfiguration definiert wird.  
  
- Die Vorgänge in diesem Vertrag werden direkt von den Methoden in der Schnittstellendefinition der Komponente abgeleitet.  
  
- Die Parameter für diese Vorgänge werden direkt von dem COM-Interoperabilitätstyp abgeleitet, der den Methodenparametern der Komponente entspricht.  
  
 Standardadressen und Transportbindungen für den Dienst werden in einer Dienstkonfigurationsdatei bereitgestellt, sie können jedoch ggf. neu konfiguriert werden.  
  
> [!NOTE]
> Die Verträge für die verfügbar gemachten Webdienste bleiben konstant, solange die COM+-Schnittstellen und die Konfiguration unverändert bleiben. Bei einer Änderung mehrerer Schnittstellen werden die verfügbaren Dienste nicht automatisch aktualisiert; das COM+ Service Model Configuration-Tool (ComSvcConfig.exe) muss jedoch erneut ausgeführt werden.  
  
 Die Authentifizierungs- und Autorisierungsanforderungen der COM+-Anwendung und ihrer Komponenten werden bei der Verwendung als Webdienst weiterhin erzwungen.  
  
 Initiiert der Aufrufer eine Webdiensttransaktion, werden als transaktionsfähig markierte Komponenten innerhalb dieses Transaktionsbereichs aufgeführt.  
  
 Die folgenden Schritte sind erforderlich, um die Schnittstelle einer COM+-Komponente ohne Änderung der Komponente als Webdienst verfügbar zu machen:  
  
1. Legen Sie fest, ob die Schnittstelle der COM+-Komponente als Webdienst verfügbar gemacht werden kann.  
  
2. Wählen Sie einen entsprechenden Hostingmodus aus.  
  
3. Verwenden Sie das COM+ Service Model Configuration-Tool (ComSvcConfig.exe) zum Hinzufügen eines Webdiensts für die Schnittstelle. Weitere Informationen zur Verwendung von ComSvcConfig. exe finden Sie unter Gewusst [wie: Verwenden des Konfigurationstools für das COM+-Dienstmodell](how-to-use-the-com-service-model-configuration-tool.md).  
  
4. Konfigurieren Sie zusätzliche Diensteinstellungen in der Anwendungskonfigurationsdatei. Weitere Informationen zum Konfigurieren einer Komponente finden Sie unter Gewusst [wie: Konfigurieren der com+-Dienst Einstellungen](how-to-configure-com-service-settings.md).  
  
## <a name="supported-interfaces"></a>Unterstützte Schnittstellen  
 Es gibt einige Beschränkungen beim Typ von Schnittstellen, die als Webdienst verfügbar gemacht werden können. Die folgenden Typen von Schnittstellen werden nicht unterstützt:  
  
- Schnittstellen, die Objektverweise als Parameter übergeben; der folgende beschränkte Objektverweisansatz wird im Abschnitt "Beschränkte Objektverweisunterstützung" beschrieben.  
  
- Schnittstellen, die Typen übergeben, die mit den .NET Framework com-Interoperabilitäts Konvertierungen nicht kompatibel sind.  
  
- Schnittstellen für Anwendungen, in denen beim Hosten durch COM+ das Anwendungspooling aktiviert ist.  
  
- Schnittstellen von Komponenten, die für die Anwendung als privat markiert sind.  
  
- COM+-Infrastrukturschnittstellen.  
  
- Schnittstellen aus der Systemanwendung.  
  
- Schnittstellen aus Enterprise Services-Komponenten, die dem globalen Assemblycache nicht hinzugefügt wurden.  
  
### <a name="limited-object-reference-support"></a>Beschränkte Objektverweisunterstützung  
 Da einige bereitgestellte COM+-Komponenten Objekte als Verweisparameter verwenden, wie Rückgabe eines ADO-Recordset-Objekts, schließt die COM+-Integration beschränkte Unterstützung für Objektverweisparameter ein. Die Unterstützung ist auf Objekte beschränkt, die die `IPersistStream`-COM-Schnittstelle implementieren. Sie schließt ADO-Recordset-Objekte ein und kann für anwendungsspezifische COM-Objekte implementiert werden.  
  
 Um diese Unterstützung zu aktivieren, stellt das Tool ComSvcConfig. exe den **allowreferences** -Schalter bereit, der den regulären Methoden Signatur Parameter deaktiviert und überprüft, ob das Tool ausgeführt wird, um sicherzustellen, dass Objekt Verweis Parameter nicht verwendet werden. Außerdem müssen die Objekttypen, die Sie als Parameter übergeben, benannt und innerhalb der <`persistableTypes`> Configuration-Elements identifiziert werden, das dem <> Element untergeordnet ist `comContract` .  
  
 Wenn diese Funktion verwendet wird, nutzt der COM+-Integrationsdienst die `IPersistStream`-Schnittstelle zum Serialisieren oder Deserialisieren der Objektinstanz. Wenn die Objektinstanz `IPersistStream` nicht unterstützt, wird eine Ausnahme ausgelöst.  
  
 In einer Clientanwendung können die Methoden im <xref:System.ServiceModel.ComIntegration.PersistStreamTypeWrapper>-Objekt zum Übergeben eines Objekt an einen Dienst und entsprechend zum Abrufen eines Objekts verwendet werden.  
  
> [!NOTE]
> Aufgrund der benutzerdefinierten und plattformspezifischen Art des Serialisierungsansatzes eignet sich dies am besten für die Verwendung zwischen WCF-Clients und WCF-Diensten.  
  
## <a name="selecting-the-hosting-mode"></a>Auswählen des Hostingmodus  
 COM+ macht Webdienste in einem der folgenden Hostingmodi verfügbar:  
  
- COM+-gehostet  
  
     Der Webdienst wird im dedizierten COM+-Serverprozess (Dllhost.exe) der Anwendung gehostet. Dieser Modus erfordert, dass die Anwendung explizit gestartet wird, bevor sie Webdienstanforderungen erhalten kann. Mit den COM+-Optionen "Als NT-Dienst ausführen" oder "Bei Leerlauf nicht herunterfahren" kann das Herunterfahren der Anwendung und ihrer Dienste bei Leerlauf verhindert werden. Dieser Modus bietet Webdiensten und DCOM Zugriff auf die Serveranwendung.  
  
- Im Internet gehostet  
  
     Der Webdienst wird in einem Webserver-Arbeitsprozess gehostet. In diesem Modus muss COM+ nicht aktiv sein, wenn die ursprüngliche Anforderung empfangen wird. Wenn die Anwendung beim Empfangen dieser Anforderung nicht aktiv ist, wird sie automatisch vor dem Verarbeiten der Anforderung aktiviert. Dieser Modus bietet ebenfalls Webdiensten und DCOM Zugriff auf die Serveranwendung, er bewirkt jedoch einen Prozesshop für Webdienstanforderungen. Dies erfordert in der Regel, dass der Client den Identitätswechsel aktiviert. In WCF kann dies mit der- <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> Eigenschaft der-Klasse erfolgen <xref:System.ServiceModel.Security.WindowsClientCredential> , auf die als Eigenschaft der generischen-Klasse zugegriffen wird, sowie mit <xref:System.ServiceModel.ChannelFactory%601> dem- <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> Enumerationswert.  
  
- Prozessintern im Internet gehostet  
  
     Der Webdienst und die COM+-Anwendungslogik werden im Webserver-Arbeitsprozess gehostet. Dieser bietet die automatische Aktivierung des Modus "Im Internet gehostet", ohne einen Prozesshop für Webdienstanforderungen zu bewirken. Der Nachteil besteht darin, dass der Zugriff auf die Serveranwendung über DCOM nicht möglich ist.  
  
### <a name="security-considerations"></a>Überlegungen zur Sicherheit  
 Wie andere WCF-Dienste werden die Sicherheitseinstellungen für den verfügbar gemachten Dienst über die Konfigurationseinstellungen für den WCF-Kanal verwaltet. Herkömmliche DCOM-Sicherheitseinstellungen wie die computerweiten DCOM-Berechtigungseinstellungen werden nicht erzwungen. Zum Erzwingen von COM+-Anwendungsrollen muss die Autorisierung "Zugriffsüberprüfungen auf der Komponentenebene" für die Komponente aktiviert werden.  
  
 Bei Verwendung einer nicht gesicherten Bindung kann für die Kommunikation die Gefahr von Manipulationen oder der Offenlegung von Informationen bestehen. Verwenden Sie eine gesicherte Bindung, um dies zu verhindern.  
  
 Für die Modi "COM+-gehostet" und "Im Internet gehostet" müssen die Clientanwendungen dem Serverprozess den Identitätswechsel für den Clientbenutzer gestatten. Dies kann in WCF-Clients erfolgen, indem die Identitätswechsel Ebene auf festgelegt wird <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> .  
  
 Wenn Internetinformationsdienste (IIS) oder Windows Process Activation Service (WAS) den HTTP-Transport verwenden, kann mit dem Tool Httpcfg.exe eine Transportendpunktadresse reserviert werden. In anderen Konfigurationen ist der Schutz vor nicht autorisierten Diensten wichtig, die als der gewünschte Dienst fungieren. Um den Start eines nicht autorisierten Dienstes am gewünschten Endpunkt zu verhindern, kann der legitime Dienst so konfiguriert werden, dass er als NT Dienst-ausgeführt wird. Dadurch hat der legitime Dienst vor jedem nicht autorisierten Dienst Anspruch auf die Endpunktadresse.  
  
 Wenn Sie eine COM+-Anwendung mit konfigurierten com+-Rollen als im Internet gehosteten Dienst verfügbar machen, muss das "IIS-Prozess Konto starten" zu einer der Rollen der Anwendung hinzugefügt werden. Dieses Konto, in der Regel mit der Bezeichnung IWAM_computername, muss hinzugefügt werden, um das saubere Herunterfahren von Objekten nach der Verwendung zu ermöglichen. Dem Konto sollten keine weiteren Berechtigungen gewährt werden.  
  
 Die COM+-Funktionen zur Prozesswiederverwendung können für integrierte Anwendungen nicht verwendet werden. Wenn die Anwendung für die Verwendung der Prozesswiederverwendung konfiguriert ist und die Komponenten in einem COM+-gehosteten Prozess ausgeführt werden, tritt beim Start des Dienstes ein Fehler auf. Diese Anforderung schließt Dienste nicht ein, die den Modus „Prozessintern im Internet gehostet“ verwenden, da die Einstellungen für die Prozesswiederverwendung nicht angewendet werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Integration von COM-Anwendungen](integrating-with-com-applications-overview.md)
