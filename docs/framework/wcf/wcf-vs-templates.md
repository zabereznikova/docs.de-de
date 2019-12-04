---
title: WCF Visual Studio-Vorlagen
ms.date: 03/30/2017
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
ms.openlocfilehash: ec73036921632bc855e79239f1fc578587de7ca3
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802348"
---
# <a name="wcf-visual-studio-templates"></a>WCF Visual Studio-Vorlagen
Windows Communication Foundation (WCF) Visual Studio-Vorlagen sind vordefinierte Projekt-und Element Vorlagen, die Sie in Visual Studio verwenden können, um schnell WCF-Dienste und umgebende Anwendungen zu erstellen.  
  
## <a name="using-the-wcf-templates"></a>Verwenden der WCF-Vorlagen  
 WCF-Visual Studio-Vorlagen stellen eine grundlegende Klassenstruktur für die Dienst Entwicklung dar. Diese Vorlagen stellen genau genommen die grundlegenden Definitionen für den Dienstvertrag, den Datenvertrag, die Dienstimplementierung und die Konfiguration bereit. Mit diesen Vorlagen können Sie einen einfachen Dienst mit minimaler Codeinteraktion sowie einen Baustein für komplexere Dienste erstellen.  
  
### <a name="wcf-service-library-project-template"></a>WCF-Dienstbibliotheksprojektvorlage  
 Die Projektvorlage der WCF-Dienst Bibliothek steht im Dialogfeld Neues Projekt unter **Visual C#\WCF** und **Visual Basic\WCF**zur Verfügung.  
  
 Wenn Sie ein neues Projekt mit der **WCF-Dienst** Vorlage erstellen, enthält das neue Projekt automatisch die folgenden drei Dateien:  
  
- Dienstvertragsdatei ("IService1.cs" oder "IService1.vb"). Die Dienstvertrags Datei ist eine Schnittstelle, auf die WCF-Dienst Attribute angewendet werden. Diese Datei enthält eine Definition eines einfachen Diensts, anhand derer Sie sehen können, wie Sie Ihre Dienste definieren können, sowie Parameter-basierte Vorgänge und ein Beispiel für einen einfachen Datenvertrag. Dies ist die Standarddatei, die nach dem Erstellen eines WCF-Dienst Projekts im Code-Editor angezeigt wird.  
  
- Dienstimplementierungsdatei (Service1.cs oder Service1.vb). Die Dienstimplementierungsdatei implementiert den in der Dienstvertragsdatei definierten Vertrag.  
  
- Anwendungskonfigurationsdatei (App.config). Die Konfigurationsdatei stellt die grundlegenden Elemente eines WCF-Dienst Modells mit einer sicheren HTTP-Bindung bereit. Sie enthält auch einen Endpunkt für den Dienst und aktiviert den Metadatenaustausch.  
  
> [!NOTE]
> Visual Studio ist so konfiguriert, dass die Datei app. config als Konfigurationsdatei für das Projekt erkannt wird, wenn es mit dem [WCF-Dienst Host (WcfSvcHost. exe)](wcf-service-host-wcfsvchost-exe.md)ausgeführt wird. Dies ist die Standardkonfiguration. Wenn als Host für die Dienstbibliothek eine EXE-Datei verwendet wird, müssen Sie den Konfigurationscode in die Konfigurationsdatei der EXE-Datei verschieben, da Konfigurationsdateien für DLL-Dateien ungültig sind.  
  
### <a name="wcf-service-application-template"></a>Vorlage für WCF-Dienstanwendungen  
 Die Vorlage WCF-Dienst Anwendung steht im Dialogfeld Neues Projekt unter  **C#Visual \WCF** und **Visual Basic\WCF**zur Verfügung.  
  
 Wenn Sie ein neues Projekt mit der **WCF-Webanwendungs-Dienst** Vorlage erstellen, enthält das Projekt die folgenden vier Dateien:  
  
- Diensthostdatei ("service1.svc").  
  
- Dienstvertragsdatei ("IService1.cs" oder "IService1.vb").  
  
- Dienstimplementierungsdatei ("Service1.svc.cs" oder "Service1.svc.vb").  
  
- Webkonfigurationsdatei ("Web.config").  
  
 Die Vorlage erstellt automatisch eine Website, die in einem virtuellen Verzeichnis eingerichtet wird, und dient zugleich als Host für einen Dienst.  
  
### <a name="wcf-web-site-template"></a>Websitevorlage für den WCF-Dienst  
 Die Vorlage für die WCF-Website steht im Dialogfeld Neues Projekt unter **Visual C#\website\wcf-Dienst** und **Visual basic\website\wcf-Dienst**zur Verfügung. Dadurch werden die gleichen Dateien wie durch die Vorlage für WCF-Dienstanwendungen erstellt, diese werden aber wie für eine ASP.NET-Website organisiert. Die Ordner App_Code und App_Data werden erstellt.  
  
### <a name="wcf-service-item-template"></a>WCF-Dienstelementvorlage  
 Die WCF-Dienst Element Vorlage ist eine benutzerdefinierte Vorlage, mit der Sie Ihren vorhandenen Visual Studio-Projekten schnell WCF-Dienste hinzufügen können.  
  
 Um diese Vorlage zu verwenden, wechseln Sie zum **Projektmappen-Explorer** Bereich, klicken Sie mit der rechten Maustaste auf den Projektnamen, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element** , um das Dialogfeld **Neues Element hinzufügen** aufzurufen  
  
 Die Dienstschnittstelle und die Implementierungsdateien werden im Stammprojektordner abgelegt.  
  
 Die Vorlage versucht, den Konfigurationsabschnitt des neuen Diensts mit einer beliebigen vorhandenen Konfigurationsdatei zusammenzuführen, sofern es sich um kompatible Typen handelt.  
  
 Eine Diensthostdatei (service1.svc) wird auch dann erstellt, wenn das vorhandene Projekt ein Webprojekt ist.  
  
### <a name="wcf-wf-service-project-and-item-template"></a>WCF-WF-Dienstprojektvorlage und Elementvorlage.  
 Diese Vorlagen erstellen WCF-Dienste, die einen Workflow Dienst hosten. dabei handelt es sich um einen Workflow, auf den wie ein Webdienst zugegriffen werden kann. Für XAML oder imperative Programmiermodelle gibt es unterschiedliche Vorlagen. Wenn Sie die Vorlagen verwenden, können Sie einen sequenziellen Workflow oder einen Zustandsautomat-Workflow erstellen. Weitere Informationen zu diesen Workflow Typen finden Sie unter Vorgehens [Weise: Erstellen eines Workflows](../windows-workflow-foundation/how-to-create-a-workflow.md). Weitere Informationen zum Erstellen von Workflow Projekten finden Sie unter [Erstellen von Legacy Workflow Projekten](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer).  
  
 Der Visual Studio-Designer reagiert besser, wenn XOML-typworkflows anstelle von Code basierten Workflows verwendet werden. Der XOML-Workflow ist der Standardworkflowtyp, der erstellt werden sollte.  
  
### <a name="wcf-syndication-service-library-template"></a>Vorlage für WCF/Syndication-Dienstbibliotheken  
 Mit dieser Vorlage können Sie Ihren Feed im RSS-oder Atom-Format als WCF-Dienst verfügbar machen. Weitere Informationen finden Sie unter [WCF-Syndikation](./feature-details/wcf-syndication.md).  
  
#### <a name="changing-the-address-of-the-feed"></a>Ändern der Adresse des Feeds  
 Die Syndication-Vorlage verwendet während der Ausführung Internet Explorer. Wenn Sie im Projektmappen- **Explorer** in Visual Studio mit der rechten Maustaste auf das Projekt klicken, wählen Sie **Eigenschaften**aus, und wählen Sie dann die Registerkarte **Debuggen** , um die Standardadresse der Vorlage anzuzeigen. Internet Explorer versucht, den Feed unter dieser Adresse zu öffnen.  
  
 Wenn Sie die Adresse des Feeds ändern, müssen Sie auch die Adresse auf der Registerkarte " **Debuggen** " ändern. Wenn Sie dies nicht tun, versucht Internet Explorer, den Feed unter der Standardadresse zu öffnen, und schlägt fehl.  
  
### <a name="ajax-enabled-wcf-service-item-template"></a>AJAX-aktivierte WCF-Dienstelementvorlage  
 Diese Vorlage stellt ein AJAX-Steuerelement als WCF-Dienst zur Verfügung. Weitere Informationen zu AJAX-Steuerelementen finden Sie in der [Dokumentation zu AJAX-Steuer](https://docs.microsoft.com/aspnet/ajax/)Elementen.  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a>Silverlight-aktivierte WCF-Dienstelementvorlage  
 Diese Vorlage erstellt einen Webdienst, der Daten für einen Silverlight-Client oder für ein Silverlight-Front-End bereitstellt. Die Vorlage kann einem Website-oder Webanwendungs Projekt hinzugefügt werden, um einen WCF-Dienst zu erstellen, der Dienst Code und die Konfiguration enthält, die die Kommunikation mit einem Silverlight-Client unterstützen. Anschließend können Sie mit **Dienstverweis hinzufügen** einen Client Proxy des Dienstanbieter zum Client hinzufügen und Daten zwischen dem Silverlight-Client und dem Silverlight-fähigen WCF-Dienst austauschen.  
  
 Um auf diese Vorlage zuzugreifen, klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf ein Website-oder ein Webanwendungs Projekt, klicken Sie auf **Neues Element hinzufügen**, und klicken Sie auf **Silverlight-aktivierter WCF**  
  
> [!NOTE]
> Der Silverlight-aktivierte WCF-Dienst macht einen `basicHttpBinding`-Endpunkt ohne aktivierte Sicherheitseinstellungen verfügbar. Deshalb können Dienstinformationen von allen Clients abgerufen werden, die eine Verbindung mit diesem Dienst herstellen. Zudem werden zwischen dem Dienst und dem Client ausgetauschte Nachrichten weder signiert noch verschlüsselt. Sichern Sie den Endpunkt nach Möglichkeit per ASP.NET-Authentifizierung, per HTTPS oder mit einem anderen Mechanismus.  
  
## <a name="see-also"></a>Siehe auch

- [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [WCF-Testclient (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
