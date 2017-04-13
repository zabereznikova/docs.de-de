---
title: "WCF Visual Studio-Vorlagen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
caps.latest.revision: 31
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 31
---
# WCF Visual Studio-Vorlagen
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Vorlagen sind vordefinierte Projekt- und Elementvorlagen, die Sie in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] verwenden können, um mühelos [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienste und entsprechende Anwendungen zu erstellen.  
  
## <a name="using-the-wcf-templates"></a>Verwenden der WCF-Vorlagen  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Vorlagen aus [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] stellen eine grundlegende Klassenstruktur zur Dienstentwicklung bereit. Diese Vorlagen stellen genau genommen die grundlegenden Definitionen für den Dienstvertrag, den Datenvertrag, die Dienstimplementierung und die Konfiguration bereit. Mit diesen Vorlagen können Sie einen einfachen Dienst mit minimaler Codeinteraktion sowie einen Baustein für komplexere Dienste erstellen.  
  
### <a name="wcf-service-library-project-template"></a>WCF-Dienstbibliotheksprojektvorlage  
 Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -dienstbibliotheksprojektvorlage steht in das Dialogfeld Neues Projekt unter **Visual C# \WCF** und **Visual Basic\WCF**.  
  
 Wenn Sie erstellen ein neues Projekt mit der **WCF-Dienst** Vorlage für das neue Projekt schließt automatisch die folgenden drei Dateien:  
  
-   Dienstvertragsdatei ("IService1.cs" oder "IService1.vb"). Die Dienstvertragsdatei ist eine Schnittstelle, auf die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstattribute angewendet wurden. Diese Datei enthält eine Definition eines einfachen Diensts, anhand derer Sie sehen können, wie Sie Ihre Dienste definieren können, sowie Parameter-basierte Vorgänge und ein Beispiel für einen einfachen Datenvertrag. Dies ist die Standarddatei, die nach dem Erstellen eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstprojekts im Code-Editor angezeigt wird.  
  
-   Dienstimplementierungsdatei (Service1.cs oder Service1.vb). Die Dienstimplementierungsdatei implementiert den in der Dienstvertragsdatei definierten Vertrag.  
  
-   Anwendungskonfigurationsdatei (App.config). Die Konfigurationsdatei stellt die Grundelemente eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstmodells mit einer sicheren HTTP-Bindung bereit. Sie enthält auch einen Endpunkt für den Dienst und aktiviert den Metadatenaustausch.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]ist so konfiguriert, dass die Datei App.config als Konfigurationsdatei für das Projekt erkennen, bei der Ausführung mit der [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md), dies ist die Standardkonfiguration. Wenn als Host für die Dienstbibliothek eine EXE-Datei verwendet wird, müssen Sie den Konfigurationscode in die Konfigurationsdatei der EXE-Datei verschieben, da Konfigurationsdateien für DLL-Dateien ungültig sind.  
  
### <a name="wcf-service-application-template"></a>Vorlage für WCF-Dienstanwendungen  
 Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Application-Vorlage steht im Dialogfeld Neues Projekt unter **Visual C# \WCF** und **Visual Basic\WCF**.  
  
 Wenn Sie erstellen ein neues Projekt mit der **WCF-Webanwendungsdienst** Vorlage für das Projekt enthält die folgenden vier Dateien:  
  
-   Diensthostdatei ("service1.svc").  
  
-   Dienstvertragsdatei ("IService1.cs" oder "IService1.vb").  
  
-   Dienstimplementierungsdatei ("Service1.svc.cs" oder "Service1.svc.vb").  
  
-   Webkonfigurationsdatei ("Web.config").  
  
 Die Vorlage erstellt automatisch eine Website, die in einem virtuellen Verzeichnis eingerichtet wird, und dient zugleich als Host für einen Dienst.  
  
### <a name="wcf-web-site-template"></a>Websitevorlage für den WCF-Dienst  
 Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Websitevorlage steht im Dialogfeld Neues Projekt unter **Visual C# \website\wcf-Dienst** und **Visual Basic\Web Site\WCF Service**. Dadurch werden die gleichen Dateien wie durch die Vorlage für WCF-Dienstanwendungen erstellt, diese werden aber wie für eine ASP.NET-Website organisiert. Die Ordner App_Code und App_Data werden erstellt.  
  
### <a name="wcf-service-item-template"></a>WCF-Dienstelementvorlage  
 Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstelementvorlage ist eine benutzerdefinierte Vorlage, über die Sie mühelos [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienste zu Ihren vorhandenen [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Projekten hinzufügen können.  
  
 Diese Vorlage verwenden, wechseln Sie zu der **Projektmappen-Explorer** Bereich mit der rechten Maustaste des Projektnamen, zeigen Sie auf **hinzufügen**, und klicken Sie dann auf **neues Element** zum Starten der **neues Element hinzufügen** Dialogfeld.  
  
 Die Dienstschnittstelle und die Implementierungsdateien werden im Stammprojektordner abgelegt.  
  
 Die Vorlage versucht, den Konfigurationsabschnitt des neuen Diensts mit einer beliebigen vorhandenen Konfigurationsdatei zusammenzuführen, sofern es sich um kompatible Typen handelt.  
  
 Eine Diensthostdatei (service1.svc) wird auch dann erstellt, wenn das vorhandene Projekt ein Webprojekt ist.  
  
### <a name="wcf-wf-service-project-and-item-template"></a>WCF-WF-Dienstprojektvorlage und Elementvorlage.  
 Mit diesen Vorlagen werden [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienste erstellt, die als Host für einen WF-Workflow fungieren. Auf diesen Workflow können Sie auf die gleiche Weise zugreifen wie auf einen Webdienst. Für XAML oder imperative Programmiermodelle gibt es unterschiedliche Vorlagen. Wenn Sie die Vorlagen verwenden, können Sie einen sequenziellen Workflow oder einen Zustandsautomat-Workflow erstellen. Weitere Informationen zu diesen Workflowtypen finden Sie unter [Windows Workflow Foundation-Lernprogramme](http://msdn.microsoft.com/de-de/e9705654-bd96-4b56-8d98-f1f118112d97). [!INCLUDE[crabout](../../../includes/crabout-md.md)]zum Erstellen von Workflowprojekten finden Sie unter [Erstellen von Legacyworkflowprojekten](../Topic/Creating%20Legacy%20Workflow%20Projects.md).  
  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Designer ist reaktionsfreudiger, wenn Workflows des Typs XOML anstelle von Code-basierten Workflows verwendet werden. Der XOML-Workflow ist der Standardworkflowtyp, der erstellt werden sollte.  
  
### <a name="wcf-syndication-service-library-template"></a>Vorlage für WCF/Syndication-Dienstbibliotheken  
 Mit dieser Vorlage können Sie den Feed im RSS- oder ATOM-Format als [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst verfügbar machen. Weitere Informationen finden Sie unter [WCF Syndication](../../../docs/framework/wcf/feature-details/wcf-syndication.md).  
  
#### <a name="changing-the-address-of-the-feed"></a>Ändern der Adresse des Feeds  
 Die Syndication-Vorlage verwendet während der Ausführung Internet Explorer. Wenn Sie mit der rechten Maustaste des Projekts in **Projektmappen-Explorer** in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]auf **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte, und Sie sehen die Standardadresse der Vorlage. Internet Explorer versucht, den Feed unter dieser Adresse zu öffnen.  
  
 Wenn Sie die Adresse Ihres Feeds ändern, müssen Sie auch die Adresse im Ändern der **Debuggen** Registerkarte. Andernfalls versucht Internet Explorer, den Feed unter der Standardadresse zu öffnen, und dieser Versuch scheitert.  
  
### <a name="ajax-enabled-wcf-service-item-template"></a>AJAX-aktivierte WCF-Dienstelementvorlage  
 Mit dieser Vorlage wird ein AJAX-Steuerelement als [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst verfügbar gemacht. Weitere Informationen über AJAX-Steuerelemente finden Sie unter der [AJAX-Steuerelement-Dokumentation](http://go.microsoft.com/fwlink/?LinkId=96717).  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a>Silverlight-aktivierte WCF-Dienstelementvorlage  
 Diese Vorlage erstellt einen Webdienst, der Daten für einen Silverlight-Client oder für ein Silverlight-Front-End bereitstellt. Die Vorlage kann einem Website- oder einem Webanwendungsprojekt hinzugefügt werden, um einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst zu erstellen, der Dienstcode und -konfiguration für die Kommunikation mit einem Silverlight-Client beinhaltet. Anschließend können Sie **Hinzufügen eines Dienstverweises** auf dem Client einen Clientproxy des Diensts hinzu, und Austauschen von Daten zwischen der Silverlight-Client und dem Silverlight-aktivierter WCF-Dienst.  
  
 Zum Aufrufen dieser Vorlage eine Website oder Anwendung mit rechten Maustaste im **Projektmappen-Explorer**, klicken Sie auf **ein neues Element hinzufügen**, und klicken Sie auf **Silverlight-aktivierter WCF-Dienst**.  
  
> [!NOTE]
>  Der Silverlight-aktivierte WCF-Dienst macht einen `basicHttpBinding`-Endpunkt ohne aktivierte Sicherheitseinstellungen verfügbar. Deshalb können Dienstinformationen von allen Clients abgerufen werden, die eine Verbindung mit diesem Dienst herstellen. Zudem werden zwischen dem Dienst und dem Client ausgetauschte Nachrichten weder signiert noch verschlüsselt. Sichern Sie den Endpunkt nach Möglichkeit per ASP.NET-Authentifizierung, per HTTPS oder mit einem anderen Mechanismus.  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)   
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)