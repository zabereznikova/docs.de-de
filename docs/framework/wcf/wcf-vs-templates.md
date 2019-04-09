---
title: WCF Visual Studio-Vorlagen
ms.date: 03/30/2017
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
ms.openlocfilehash: b0cca0cd585a45b795db4d573659e0d19ecd78dc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130896"
---
# <a name="wcf-visual-studio-templates"></a>WCF Visual Studio-Vorlagen
Windows Communication Foundation (WCF) von Visual Studio-Vorlagen sind vordefinierte Projekt- und Elementvorlagen, die Sie in Visual Studio verwenden können, um WCF-Dienste und entsprechende Anwendungen schnell zu erstellen.  
  
## <a name="using-the-wcf-templates"></a>Verwenden der WCF-Vorlagen  
 WCF Visual Studio-Vorlagen stellen eine grundlegende Klassenstruktur zur Dienstentwicklung bereit. Diese Vorlagen stellen genau genommen die grundlegenden Definitionen für den Dienstvertrag, den Datenvertrag, die Dienstimplementierung und die Konfiguration bereit. Mit diesen Vorlagen können Sie einen einfachen Dienst mit minimaler Codeinteraktion sowie einen Baustein für komplexere Dienste erstellen.  
  
### <a name="wcf-service-library-project-template"></a>WCF-Dienstbibliotheksprojektvorlage  
 Der WCF-Dienstbibliothek-Projektvorlage ist verfügbar, in das Dialogfeld Neues Projekt unter **Visual C# \WCF** und **Visual Basic\WCF**.  
  
 Bei der Erstellung ein neues Projekt mit der **WCF-Dienst** Vorlage für das neue Projekt schließt automatisch die folgenden drei Dateien:  
  
-   Dienstvertragsdatei ("IService1.cs" oder "IService1.vb"). Die dienstvertragsdatei ist eine Schnittstelle, die WCF-Dienst-Attribute, die angewendet wurde. Diese Datei enthält eine Definition eines einfachen Diensts, anhand derer Sie sehen können, wie Sie Ihre Dienste definieren können, sowie Parameter-basierte Vorgänge und ein Beispiel für einen einfachen Datenvertrag. Dies ist die Standarddatei, die nach dem Erstellen eines WCF-Dienst-Projekts im Code-Editor angezeigt.  
  
-   Dienstimplementierungsdatei (Service1.cs oder Service1.vb). Die Dienstimplementierungsdatei implementiert den in der Dienstvertragsdatei definierten Vertrag.  
  
-   Anwendungskonfigurationsdatei (App.config). Die Konfigurationsdatei enthält die grundlegenden Elemente eines WCF-Dienstmodells mit einer sicheren HTTP-Bindung. Sie enthält auch einen Endpunkt für den Dienst und aktiviert den Metadatenaustausch.  
  
> [!NOTE]
>  Visual Studio ist so konfiguriert, dass die Datei "App.config" als der Konfigurationsdatei für das Projekt erkannt wird, wenn er ausgeführt wird, mit der [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md), dies ist die Standardkonfiguration. Wenn als Host für die Dienstbibliothek eine EXE-Datei verwendet wird, müssen Sie den Konfigurationscode in die Konfigurationsdatei der EXE-Datei verschieben, da Konfigurationsdateien für DLL-Dateien ungültig sind.  
  
### <a name="wcf-service-application-template"></a>Vorlage für WCF-Dienstanwendungen  
 Die Dienstanwendung für WCF-Vorlage steht im Dialogfeld "Neues Projekt" unter **Visual C# \WCF** und **Visual Basic\WCF**.  
  
 Bei der Erstellung ein neues Projekt mit der **WCF-Webanwendungsdienst** Vorlage für das Projekt enthält die folgenden vier Dateien:  
  
-   Diensthostdatei ("service1.svc").  
  
-   Dienstvertragsdatei ("IService1.cs" oder "IService1.vb").  
  
-   Dienstimplementierungsdatei ("Service1.svc.cs" oder "Service1.svc.vb").  
  
-   Webkonfigurationsdatei ("Web.config").  
  
 Die Vorlage erstellt automatisch eine Website, die in einem virtuellen Verzeichnis eingerichtet wird, und dient zugleich als Host für einen Dienst.  
  
### <a name="wcf-web-site-template"></a>Websitevorlage für den WCF-Dienst  
 Der WCF--Websitevorlage steht im Dialogfeld "Neues Projekt" unter **Visual C# \Web Site\WCF Service** und **basic\website\wcf-Dienst von Visual Basic\Web**. Dadurch werden die gleichen Dateien wie durch die Vorlage für WCF-Dienstanwendungen erstellt, diese werden aber wie für eine ASP.NET-Website organisiert. Die Ordner App_Code und App_Data werden erstellt.  
  
### <a name="wcf-service-item-template"></a>WCF-Dienstelementvorlage  
 Die Elementvorlage für WCF-Dienst ist eine benutzerdefinierte Vorlage, die eine schnelle Möglichkeit zum Hinzufügen von WCF-Dienste auf Ihren vorhandenen Visual Studio-Projekten bereitstellt.  
  
 Um diese Vorlage verwenden möchten, wechseln Sie zu der **Projektmappen-Explorer** Bereich mit der rechten Maustaste des Projektnamen, zeigen Sie auf **hinzufügen**, und klicken Sie dann auf **neues Element** zum Starten der **neu hinzufügen Element** Dialogfeld.  
  
 Die Dienstschnittstelle und die Implementierungsdateien werden im Stammprojektordner abgelegt.  
  
 Die Vorlage versucht, den Konfigurationsabschnitt des neuen Diensts mit einer beliebigen vorhandenen Konfigurationsdatei zusammenzuführen, sofern es sich um kompatible Typen handelt.  
  
 Eine Diensthostdatei (service1.svc) wird auch dann erstellt, wenn das vorhandene Projekt ein Webprojekt ist.  
  
### <a name="wcf-wf-service-project-and-item-template"></a>WCF-WF-Dienstprojektvorlage und Elementvorlage.  
 Diese Vorlagen erstellen WCF-Dienste, Hosten eines Workflowdiensts, d.h., dass ein Workflow, der wie ein Webdienst zugegriffen werden kann. Für XAML oder imperative Programmiermodelle gibt es unterschiedliche Vorlagen. Wenn Sie die Vorlagen verwenden, können Sie einen sequenziellen Workflow oder einen Zustandsautomat-Workflow erstellen. Weitere Informationen zu diesen Workflowtypen finden Sie unter [Vorgehensweise: Erstellen eines Workflows](../windows-workflow-foundation/how-to-create-a-workflow.md). Weitere Informationen zum Erstellen von Workflowprojekten finden Sie unter [Erstellen von Legacyworkflowprojekten](/visualstudio/workflow-designer/creating-legacy-workflow-projects).  
  
 Visual Studio-Designer reagiert besser aus, wenn Typs XOML Workflows verwendet werden stattdessen Code solche basierend. Der XOML-Workflow ist der Standardworkflowtyp, der erstellt werden sollte.  
  
### <a name="wcf-syndication-service-library-template"></a>Vorlage für WCF/Syndication-Dienstbibliotheken  
 Mit dieser Vorlage können Sie den Feed im RSS- oder ATOM-Format als WCF-Dienst verfügbar machen. Weitere Informationen finden Sie unter [WCF Syndication](../../../docs/framework/wcf/feature-details/wcf-syndication.md).  
  
#### <a name="changing-the-address-of-the-feed"></a>Ändern der Adresse des Feeds  
 Die Syndication-Vorlage verwendet während der Ausführung Internet Explorer. Wenn Sie mit der rechten Maustaste des Projekts im **Projektmappen-Explorer** wählen Sie in Visual Studio **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte, und Sie sehen die Standardadresse für die Vorlage. Internet Explorer versucht, den Feed unter dieser Adresse zu öffnen.  
  
 Wenn Sie die Adresse Ihres Feed ändern, müssen Sie auch ändern, auf die Adresse in der **Debuggen** Registerkarte. Andernfalls versucht Internet Explorer, den Feed unter der Standardadresse zu öffnen, und dieser Versuch scheitert.  
  
### <a name="ajax-enabled-wcf-service-item-template"></a>AJAX-aktivierte WCF-Dienstelementvorlage  
 Diese Vorlage stellt ein AJAX-Steuerelement als ein WCF-Dienst. Weitere Informationen zu AJAX-Steuerelementen finden Sie unter den [AJAX-Steuerelement Dokumentation](https://go.microsoft.com/fwlink/?LinkId=96717).  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a>Silverlight-aktivierte WCF-Dienstelementvorlage  
 Diese Vorlage erstellt einen Webdienst, der Daten für einen Silverlight-Client oder für ein Silverlight-Front-End bereitstellt. Die Vorlage kann einem Website- oder Webanwendungsprojekt-Anwendungsprojekt, um einen WCF-Dienst zu erstellen, der Dienstcode und-Konfiguration für die Kommunikation mit einem Silverlight-Client umfasst hinzugefügt werden. Anschließend können Sie **Hinzufügen eines Dienstverweises** einen Clientproxy des Diensts an den Client hinzufügen und Austauschen von Daten zwischen der Silverlight-Client und dem Silverlight-aktivierte WCF-Dienst.  
  
 Maustaste Sie diese Vorlage für den Zugriff auf eine Website oder einem Webanwendungsprojekt in **Projektmappen-Explorer**, klicken Sie auf **Hinzufügen eines neuen Elements**, und klicken Sie auf **Silverlight-aktivierter WCF-Dienst**.  
  
> [!NOTE]
>  Der Silverlight-aktivierte WCF-Dienst macht einen `basicHttpBinding`-Endpunkt ohne aktivierte Sicherheitseinstellungen verfügbar. Deshalb können Dienstinformationen von allen Clients abgerufen werden, die eine Verbindung mit diesem Dienst herstellen. Zudem werden zwischen dem Dienst und dem Client ausgetauschte Nachrichten weder signiert noch verschlüsselt. Sichern Sie den Endpunkt nach Möglichkeit per ASP.NET-Authentifizierung, per HTTPS oder mit einem anderen Mechanismus.  
  
## <a name="see-also"></a>Siehe auch

- [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
- [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
