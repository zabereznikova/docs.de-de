---
title: WCF Visual Studio-Vorlagen
ms.date: 03/30/2017
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
ms.openlocfilehash: 13183ad5f05350c34eebd025eca3faa7d97644f8
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608022"
---
# <a name="wcf-visual-studio-templates"></a>WCF Visual Studio-Vorlagen
Windows Communication Foundation (WCF)-Visual Studio-Vorlagen sind vordefinierte Projekt- und Elementvorlagen, die Sie in Visual Studio verwenden können, um WCF-Dienste und umgebende Anwendungen schnell zu erstellen.  
  
## <a name="using-the-wcf-templates"></a>Verwenden der WCF-Vorlagen  
 WCF Visual Studio-Vorlagen stellen eine grundlegende Klassenstruktur für die Dienstentwicklung bereit. Diese Vorlagen stellen genau genommen die grundlegenden Definitionen für den Dienstvertrag, den Datenvertrag, die Dienstimplementierung und die Konfiguration bereit. Mit diesen Vorlagen können Sie einen einfachen Dienst mit minimaler Codeinteraktion sowie einen Baustein für komplexere Dienste erstellen.  
  
### <a name="wcf-service-library-project-template"></a>WCF-Dienstbibliotheksprojektvorlage  
 Die Projektvorlage wCF-Dienstbibliothek ist im neuen Projektdialogfeld unter **Visual C-WCF** und **Visual Basic -WCF**verfügbar.  
  
 Wenn Sie ein neues Projekt mit der **WCF-Dienstvorlage** erstellen, enthält das neue Projekt automatisch die folgenden drei Dateien:  
  
- Dienstvertragsdatei ("IService1.cs" oder "IService1.vb"). Die Dienstvertragsdatei ist eine Schnittstelle, auf die WCF-Dienstattribute angewendet werden. Diese Datei enthält eine Definition eines einfachen Diensts, anhand derer Sie sehen können, wie Sie Ihre Dienste definieren können, sowie Parameter-basierte Vorgänge und ein Beispiel für einen einfachen Datenvertrag. Dies ist die Standarddatei, die im Code-Editor angezeigt wird, nachdem ein WCF-Dienstprojekt erstellt wurde.  
  
- Dienstimplementierungsdatei (Service1.cs oder Service1.vb). Die Dienstimplementierungsdatei implementiert den in der Dienstvertragsdatei definierten Vertrag.  
  
- Anwendungskonfigurationsdatei (App.config). Die Konfigurationsdatei stellt die grundlegenden Elemente eines WCF-Dienstmodells mit einer sicheren HTTP-Bindung bereit. Sie enthält auch einen Endpunkt für den Dienst und aktiviert den Metadatenaustausch.  
  
> [!NOTE]
> Visual Studio ist so konfiguriert, dass die Datei App.config als Konfigurationsdatei für das Projekt erkannt wird, wenn sie mit dem [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)ausgeführt wird, der die Standardkonfiguration ist. Wenn als Host für die Dienstbibliothek eine EXE-Datei verwendet wird, müssen Sie den Konfigurationscode in die Konfigurationsdatei der EXE-Datei verschieben, da Konfigurationsdateien für DLL-Dateien ungültig sind.  
  
### <a name="wcf-service-application-template"></a>Vorlage für WCF-Dienstanwendungen  
 Die WCF-Dienstanwendungsvorlage ist im Dialogfeld Neues Projekt unter **Visual C-WCF** und **Visual Basic -WCF**verfügbar.  
  
 Wenn Sie ein neues Projekt mit der **WCF-Webanwendungsdienstvorlage** erstellen, enthält das Projekt die folgenden vier Dateien:  
  
- Diensthostdatei ("service1.svc").  
  
- Dienstvertragsdatei ("IService1.cs" oder "IService1.vb").  
  
- Dienstimplementierungsdatei ("Service1.svc.cs" oder "Service1.svc.vb").  
  
- Webkonfigurationsdatei ("Web.config").  
  
 Die Vorlage erstellt automatisch eine Website, die in einem virtuellen Verzeichnis eingerichtet wird, und dient zugleich als Host für einen Dienst.  
  
### <a name="wcf-web-site-template"></a>Websitevorlage für den WCF-Dienst  
 Die WCF-Websitevorlage ist im Dialogfeld Neues Projekt unter **Visual C-Website-WCF-Dienst** und **Visual Basic-Website-WCF-Dienst**verfügbar. Dadurch werden die gleichen Dateien wie durch die Vorlage für WCF-Dienstanwendungen erstellt, diese werden aber wie für eine ASP.NET-Website organisiert. Die Ordner App_Code und App_Data werden erstellt.  
  
### <a name="wcf-service-item-template"></a>WCF-Dienstelementvorlage  
 Die WCF-Dienstelementvorlage ist eine benutzerdefinierte Vorlage, die eine schnelle Möglichkeit bietet, WCF-Dienste zu Ihren vorhandenen Visual Studio-Projekten hinzuzufügen.  
  
 Um diese Vorlage zu verwenden, wechseln Sie zum **Projektmappen-Explorer,** klicken Sie mit der rechten Maustaste auf Ihren Projektnamen, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element,** um das Dialogfeld **Neues Element hinzufügen** zu starten.  
  
 Die Dienstschnittstelle und die Implementierungsdateien werden im Stammprojektordner abgelegt.  
  
 Die Vorlage versucht, den Konfigurationsabschnitt des neuen Diensts mit einer beliebigen vorhandenen Konfigurationsdatei zusammenzuführen, sofern es sich um kompatible Typen handelt.  
  
 Eine Diensthostdatei (service1.svc) wird auch dann erstellt, wenn das vorhandene Projekt ein Webprojekt ist.  
  
### <a name="wcf-wf-service-project-and-item-template"></a>WCF-WF-Dienstprojektvorlage und Elementvorlage.  
 Diese Vorlagen erstellen WCF-Dienste, die einen Workflowdienst hosten, bei dem es sich um einen Workflow handelt, auf den wie ein Webdienst zugegriffen werden kann. Für XAML oder imperative Programmiermodelle gibt es unterschiedliche Vorlagen. Wenn Sie die Vorlagen verwenden, können Sie einen sequenziellen Workflow oder einen Zustandsautomat-Workflow erstellen. Weitere Informationen zu diesen Workflowtypen finden Sie unter [Gewusst wie: Erstellen eines Workflows](../windows-workflow-foundation/how-to-create-a-workflow.md). Weitere Informationen zum Erstellen von Workflowprojekten finden Sie unter [Erstellen von Legacyworkflowprojekten](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer).  
  
 Der Visual Studio-Designer reagiert reaktionsschneller, wenn Workflows vom XOML-Typ anstelle von Codebasierten verwendet werden. Der XOML-Workflow ist der Standardworkflowtyp, der erstellt werden sollte.  
  
### <a name="wcf-syndication-service-library-template"></a>Vorlage für WCF/Syndication-Dienstbibliotheken  
 Mit dieser Vorlage können Sie Ihren Feed im RSS- oder ATOM-Format als WCF-Dienst verfügbar machen. Weitere Informationen finden Sie unter [WCF Syndication](./feature-details/wcf-syndication.md).  
  
#### <a name="changing-the-address-of-the-feed"></a>Ändern der Adresse des Feeds  
 Die Syndication-Vorlage verwendet während der Ausführung Internet Explorer. Wenn Sie im **Projekt-Explorer** in Visual Studio mit der rechten Maustaste auf Ihr Projekt klicken, wählen Sie **Eigenschaften**aus, und wählen Sie dann die Registerkarte **Debuggen** aus, und Sie können die Standardadresse der Vorlage anzeigen. Internet Explorer versucht, den Feed unter dieser Adresse zu öffnen.  
  
 Wenn Sie die Adresse Ihres Feeds ändern, müssen Sie auch die Adresse auf der Registerkarte **Debugdebug** ändern. Wenn Sie dies nicht tun, versucht Internet Explorer, den Feed unter der Standardadresse zu öffnen, und schlägt fehl.  
  
### <a name="ajax-enabled-wcf-service-item-template"></a>AJAX-aktivierte WCF-Dienstelementvorlage  
 Diese Vorlage macht ein AJAX-Steuerelement als WCF-Dienst verfügbar. Weitere Informationen zu AJAX-Steuerelementen finden Sie in der [AJAX-Steuerelementdokumentation](/aspnet/ajax/).  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a>Silverlight-aktivierte WCF-Dienstelementvorlage  
 Diese Vorlage erstellt einen Webdienst, der Daten für einen Silverlight-Client oder für ein Silverlight-Front-End bereitstellt. Die Vorlage kann einer Website oder einem Webanwendungsprojekt hinzugefügt werden, um einen WCF-Dienst zu erstellen, der Servicecode und Konfiguration umfasst, die die Kommunikation mit einem Silverlight-Client unterstützen. Sie können dann **Dienstreferenz hinzufügen** verwenden, um dem Client einen Clientproxy des Dienstes hinzuzufügen und Daten zwischen dem Silverlight-Client und dem Silverlight-fähigen WCF-Dienst auszutauschen.  
  
 Um auf diese Vorlage zuzugreifen, klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf eine Website oder ein Webanwendungsprojekt , klicken Sie auf **Neues Element hinzufügen**, und klicken Sie auf **Silverlight-aktivierter WCF-Dienst**.  
  
> [!NOTE]
> Der Silverlight-aktivierte WCF-Dienst macht einen `basicHttpBinding`-Endpunkt ohne aktivierte Sicherheitseinstellungen verfügbar. Deshalb können Dienstinformationen von allen Clients abgerufen werden, die eine Verbindung mit diesem Dienst herstellen. Zudem werden zwischen dem Dienst und dem Client ausgetauschte Nachrichten weder signiert noch verschlüsselt. Sichern Sie den Endpunkt nach Möglichkeit per ASP.NET-Authentifizierung, per HTTPS oder mit einem anderen Mechanismus.  
  
## <a name="see-also"></a>Siehe auch

- [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [WCF-Testclient (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
