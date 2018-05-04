---
title: 'Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application services host [client application services]
- client application services, walkthroughs
ms.assetid: bb7c8950-4517-4dae-b705-b74a14059b26
caps.latest.revision: 47
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fe0e446a0005ffcbf296c2728fd93056c3e38f2a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-using-client-application-services"></a>Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten
In diesem Thema wird beschrieben, wie eine Windows-Anwendung erstellen, die Clientanwendungsdienste zum Authentifizieren von Benutzern und zum Abrufen von Benutzerrollen und Einstellungen verwendet wird.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:  
  
-   In diesem Thema wird beschrieben, wie Sie den [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Projekt-Designer zum Aktivieren und Konfigurieren von Clientanwendungsdiensten verwenden.  
  
-   Erstellen Sie eine einfache ASP.NET Web Service-Anwendung, um die Anwendungsdienste zu hosten und Ihre Clientkonfiguration zu testen.  
  
-   Fügen Sie die Formularauthentifizierung zur Anwendung hinzu. Sie beginnen mit einem hartcodierten Benutzernamen und einem Kennwort, um den Dienst zu testen Anschließend fügen Sie in der Anwendungskonfiguration ein Anmeldeformular als Anmeldeinformationsanbieter hinzu.  
  
-   Fügen Sie rollenbasierte Funktionen hinzu, wodurch eine Schaltfläche nur für Benutzer in der Rolle „Manager“ aktiviert und eingeblendet wird.  
  
-   Greifen Sie auf die Webeinstellungen zu. Sie zunächst laden Sie Webeinstellungen für einen authentifizierten (Test)-Benutzer auf die Seite **Einstellungen** im Projekt-Designer. Dann verwenden Sie den Windows Forms-Designer, um ein Textfeld an eine Webeinstellung zu binden. Speichern Sie abschließend den geänderten Wert wieder auf dem Server.  
  
-   Implementieren Sie die Abmeldung. Sie fügen dem Formular eine Abmeldeoption hinzu und rufen Sie eine Abmeldemethode auf.  
  
-   Aktivieren Sie den Offline-Modus. Sie stellen ein Kontrollkästchen bereit, damit Benutzer ihren Verbindungsstatus angeben können. Anschließend verwenden Sie diesen Wert, um anzugeben, ob die Anbieter von Clientanwendungsdiensten lokal zwischengespeicherte Daten verwenden, anstatt auf ihre Webdienste zuzugreifen. Schließlich authentifizieren Sie den aktuellen Benutzer erneut, wenn die Anwendung zurück in den Onlinemodus wechselt.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_orcas_long](../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-client-application"></a>Erstellen der Clientanwendung  
 Zunächst erstellen Sei ein Windows Forms-Projekt. In dieser exemplarischen Vorgehensweise wird Windows Forms verwendet, da damit mehr Benutzer vertraut sind. Der Vorgang ist jedoch bei Windows Presentation Foundation (WPF)-Projekten ähnlich.  
  
#### <a name="to-create-a-client-application-and-enable-client-application-services"></a>So erstellen Sie eine Clientanwendung und aktivieren Sie Clientanwendungsdienste:  
  
1.  Wählen Sie unter [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] die Menüoption **Datei &#124; Neu &#124; Projekt** aus.  
  
2.  Erweitern Sie im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** den **Visual Basic**- oder **Visual C#**-Knoten, und wählen Sie den **Windows**-Projekttyp aus.  
  
3.  Stellen Sie sicher, dass **.NET Framework 3.5** ausgewählt ist, und wählen Sie dann die **Windows Forms-Anwendung** -Vorlage aus.  
  
4.  Ändern Sie den **Namen** des Projekts in `ClientAppServicesDemo`, und klicken Sie dann auf **OK**.  
  
     Ein neues Windows Forms-Projekt wird in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]geöffnet.  
  
5.  Wählen Sie aus dem Menü **Projekt** die Option **ClientAppServicesDemo-Eigenschaften**.  
  
     Der Projekt-Designer wird angezeigt.  
  
6.  Wählen Sie auf der Registerkarte **Dienste** die Option **Clientanwendungsdienste aktivieren**aus.  
  
7.  Stellen Sie sicher, dass **Formularauthentifizierung verwenden** ausgewählt ist, und legen Sie dann **Speicherort des Authentifizierungsdiensts**, **Speicherort des Rollendiensts**und **Speicherort des Webeinstellungsdienstes** auf `http://localhost:55555/AppServices`fest.  
  
8.  Legen Sie den **Authentifizierungsmodus** für Visual Basic in der Registerkarte **Anwendung** auf **Anwendungsdefiniert** fest.  
  
 Der Designer speichert die festgelegten Einstellungen in der app.config-Datei der Anwendung.  
  
 An diesem Punkt ist die Anwendung darauf konfiguriert, von demselben Host auf alle drei Dienste zuzugreifen. Im nächsten Abschnitt erstellen Sie den Host als einfache Webdienstanwendung, wodurch Sie ihre  Clientkonfiguration testen können.  
  
## <a name="creating-the-application-services-host"></a>Erstellen des Anwendungsdienst-Hostes  
 In diesem Abschnitt erstellen Sie eine einfache Webdienstanwendung, die auf Benutzerdaten aus einer lokalen SQL Server Compact-Datenbankdatei zugreift. Anschließend füllen Sie die Datenbank mit [ASP.NET Web Site Administration Tool](http://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec)auf. Mit dieser einfachen Konfiguration können Sie die Clientanwendung schnell überprüfen. Alternativ können Sie den Webdiensthost so konfigurieren, dass er auf Benutzerdaten aus einer vollständigen SQL Server-Datenbank oder durch benutzerdefinierte Klassen <xref:System.Web.Security.MembershipProvider> und <xref:System.Web.Security.RoleProvider> zugreift. Weitere Informationen finden Sie unter [Creating and Configuring the Application Services Database for SQL Server](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2).  
  
 Im folgenden Verfahren erstellen und konfigurieren Sie den AppServices-Webdienst.  
  
#### <a name="to-create-and-configure-the-application-services-host"></a>So erstellen und konfigurieren Sie den Anwendungsdienst-Host:  
  
1.  Wählen Sie im **Projektmappen-Explorer** die ClientAppServicesDemo-Projektmappe aus. Wählen Sie dann im Menü **Datei** die Option **Hinzufügen &#124; Neues Projekt** aus.  
  
2.  Erweitern Sie im Dialogfeld **Neues Projekt hinzufügen** im Bereich **Projekttypen** den **Visual Basic**- oder **Visual C#**-Knoten, und wählen Sie den **Web**-Projekttyp aus.  
  
3.  Stellen Sie sicher, dass **.NET Framework 3.5** ausgewählt ist, und wählen Sie dann die **ASP .NET-Webdienstanwendung** -Vorlage aus.  
  
4.  Ändern Sie den **Namen** des Projekts in `AppServices` , und klicken Sie dann auf **OK**.  
  
     Ein neues ASP.NET Web Service-Anwendungsprojekt wird der Projektmappe hinzugefügt, und die Datei Service1.asmx.vb oder Service1.asmx.cs wird im Editor angezeigt.  
  
    > [!NOTE]
    >  Die Datei Service1.asmx.vb oder Service1.asmx.cs wird in diesem Beispiel nicht verwendet. Wenn die Arbeitsumgebung übersichtlich bleiben soll, können Sie sie schließen und aus dem **Projektmappen-Explorer**löschen.  
  
5.  Wählen Sie im **Projektmappen-Explorer**das AppServices-Projekt aus. Wählen Sie dann im Menü **Projekt** die Option **AppServices-Eigenschaften**aus.  
  
     Der Projekt-Designer wird angezeigt.  
  
6.  Stellen Sie auf der Registerkarte **Web** sicher, dass **Mit Visual Studio Development Server** ausgewählt ist.  
  
7.  Wählen Sie **Bestimmter Port**, geben Sie den Wert `55555`ein, und legen Sie dann den **virtuellen Pfad** auf `/AppServices`fest.  
  
8.  Speichern Sie alle Dateien.  
  
9. Öffnen Sie im **Projektmappen-Explorer**die Web.config und suchen Sie nach dem `<system.web>` Öffnungstag.  
  
10. Fügen Sie das folgende Markup vor Tag `<system.web>` hinzu.  
  
     Mithilfe der Elemente `authenticationService`, `profileService`und `roleService` in diesem Markup werden die Anwendungsdienste aktiviert und konfiguriert. Für Testzwecke wird das Attribut `requireSSL` des Elements `authenticationService` auf „false“ festgelegt. Die Attribute `readAccessProperties` und `writeAccessProperties` des Elements `profileService` zeigen an, dass die Eigenschaft `WebSettingsTestText` schreibgeschützt ist.  
  
    > [!NOTE]
    >  In Produktionscode sollten Sie auf den Authentifizierungsdienst stets über SSL (Secure Sockets Layer; unter Verwendung des HTTPS-Protokolls) zugreifen. Weitere Informationen zum Einrichten von SSL finden Sie unter [Konfigurieren von SSL (Secure Sockets Layer) (Bedienerhandbuch zu IIS 6.0)](http://go.microsoft.com/fwlink/?LinkId=91844).  
  
    ```xml  
    <system.web.extensions>  
      <scripting>  
        <webServices>  
          <authenticationService enabled="true" requireSSL = "false"/>  
          <profileService enabled="true"  
            readAccessProperties="WebSettingsTestText"  
            writeAccessProperties="WebSettingsTestText" />  
          <roleService enabled="true"/>  
        </webServices>  
      </scripting>  
    </system.web.extensions>  
    ```  
  
11. Fügen Sie das folgende Markup nach dem  Öffnungstag `<system.web>` hinzu, sodass es sich innerhalb des Elements `<system.web>` befindet.  
  
     Das Element `profile` konfiguriert eine einzelne Webeinstellung mit dem Namen `WebSettingsTestText`.  
  
    ```xml  
    <profile enabled="true" >  
      <properties>  
        <add name="WebSettingsTestText" type="string"   
          readOnly="false" defaultValue="DefaultText"   
          serializeAs="String" allowAnonymous="false" />  
      </properties>  
    </profile>  
    ```  
  
 Im folgenden Verfahren verwenden Sie das ASP.NET Websiteverwaltungs-Tool, um die Dienstkonfiguration abzuschließen und die lokale Datenbankdatei aufzufüllen. Fügen Sie zwei Benutzer mit dem Namen `employee` und `manager` zu zwei Rollen mit denselben Namen hinzu. Die Benutzerkennwörter lauten `employee!` bzw. `manager!` .  
  
#### <a name="to-configure-membership-and-roles"></a>So konfigurieren Sie die Mitgliedschaft und Rollen:  
  
1.  Wählen Sie im **Projektmappen-Explorer**das AppServices-Projekt aus. Wählen Sie dann im Menü **Projekt** die Option **ASP .NET-Konfiguration**aus.  
  
     Das **ASP.NET-Websiteverwaltungs-Tool** wird aufgerufen.  
  
2.  Klicken Sie auf der Registerkarte **Sicherheit** auf **„Verwenden des Sicherheits-Setup-Assistenten“, um die Sicherheit Schritt für Schritt zu konfigurieren.**  
  
     Die **Sicherheits-Setup-Assistent** wird geöffnet und zeigt den **Begrüßungsschritt** an.  
  
3.  Klicken Sie auf **Weiter**.  
  
     Es wird der Schritt **Zugriffsmethode auswählen** angezeigt.  
  
4.  Wählen Sie **Aus dem Internet**. Dadurch wird der Dienst auf die Nutzung der Formularauthentifizierung statt der Windows-Authentifizierung konfiguriert.  
  
5.  Klicken Sie zweimal auf **Weiter** .  
  
     Der Schritt **Rollen definieren** wird angezeigt.  
  
6.  Wählen Sie **Aktivieren von Rollen für diese Website**.  
  
7.  Klicken Sie auf **Weiter**. Das Formular **Neue Rolle erstellen** wird angezeigt.  
  
8.  Geben Sie in das Textfeld **Name der neuen Rolle** den Wert `manager` ein. Klicken Sie dann auf **Rolle hinzufügen**.  
  
     Die Tabelle **Vorhandene Rollen** wird mit dem angegebenen Wert angezeigt.  
  
9. Ersetzen Sie im Textfeld **Name der neuen Rolle** den Wert `manager` durch `employee` . Klicken Sie dann auf **Rolle hinzufügen**.  
  
     Der neue Wert wird in der Tabelle **vorhandene Rollen** angezeigt.  
  
10. Klicken Sie auf **Weiter**.  
  
     Der Schritt **neue Benutzer hinzufügen** wird angezeigt.  
  
11. Legen Sie im Formular **Benutzer erstellen** die folgenden Werte fest:  
  
  	|||  
  	|-|-|  
  	|**Benutzername**|`manager`|  
  	|**Kennwort**|`manager!`|  
  	|**Kennwort bestätigen**|`manager!`|  
  	|**E-Mail**|`manager@contoso.com`|  
  	|**Sicherheitsfrage**|`manager`|  
  	|**Sicherheitsantwort**|`manager`|  
  
12. Klicken Sie auf **Benutzer erstellen**  
  
     Eine Erfolgsmeldung wird eingeblendet.  
  
    > [!NOTE]
    >  Die Werte für **E-Mail**, **Sicherheitsfrage**, und **Sicherheitsantwort** werden vom Formular benötigt, in diesem Beispiel jedoch nicht verwendet.  
  
13. Klicken Sie auf **Weiter**.  
  
     Das Formular **Benutzer erstellen** wird erneut angezeigt.  
  
14. Legen Sie im Formular **Benutzer erstellen** die folgenden Werte fest:  
  
  	|||  
  	|-|-|  
  	|**Benutzername**|`employee`|  
  	|**Kennwort**|`employee!`|  
  	|**Kennwort bestätigen**|`employee!`|  
  	|**E-Mail**|`employee@contoso.com`|  
  	|**Sicherheitsfrage**|`Employee`|  
  	|**Sicherheitsantwort**|`employee`|  
  
15. Klicken Sie auf **Benutzer erstellen**  
  
     Eine Erfolgsmeldung wird eingeblendet.  
  
16. Klicken Sie auf **Fertig stellen**.  
  
     Das **Websiteverwaltungs-Tool** wird wieder eingeblendet.  
  
17. Klicken Sie auf **Manager-Benutzer**.  
  
     Die Liste der Benutzer wird angezeigt.  
  
18. Klicken Sie auf **Rollen bearbeiten** für die **Mitarbeiter** -Benutzer, und wählen Sie dann die **Mitarbeiter** -Rolle aus.  
  
19. Klicken Sie auf **Rollen bearbeiten** für den **Manager** -Benutzer, und wählen Sie dann die **Manager** -Rolle aus.  
  
20. Schließen Sie das Browserfenster, in dem das **Websiteverwaltungs-Tool**gehostet wird.  
  
21. Wenn ein Meldungsfeld eingeblendet wird, in dem Sie gefragt werden, ob Sie die geänderte Datei Web.config erneut laden möchten, klicken Sie auf **Ja**.  
  
 Dadurch wird die Einrichtung des Webdiensts abgeschlossen. Sie können nun auf F5 drücken, um die Client-Anwendung auszuführen. Der **ASP.NET Development Server** wird automatisch zusammen mit der Clientanwendung gestartet. Der Server wird weiter ausgeführt, nachdem Sie die Anwendung beenden, er wird jedoch bei einem Neustart der Anwendung neu hochgefahren. Dadurch können alle an der Web.config vorgenommenen Änderungen erkannt werden.  
  
 Um den Server manuell zu stoppen, klicken Sie im Infobereich der Taskleiste mit der rechten Maustaste auf ASP.NET Development Server. Klicken Sie dann auf **Stopp**. Dies empfiehlt sich gelegentlich, um einen reibungslosen Neustart zu gewährleisten.  
  
## <a name="adding-forms-authentication"></a>Hinzufügen der Formularauthentifizierung  
 Im folgenden Verfahren fügen Sie Code zum Hauptformular hinzu, der versucht, den Benutzer zu validieren. Er verweigert den Zugang, wenn der Benutzer ungültige Anmeldeinformationen bereitstellt. Sie verwenden einen hartcodierten Benutzernamen und ein Kennwort, um den Dienst zu testen  
  
#### <a name="to-validate-the-user-in-your-application-code"></a>So überprüfen Sie den Benutzer im Anwendungscode:  
  
1.  Fügen Sie im **Projektmappen-Explorer** im Projekt ClientAppServicesDemo einen Verweis auf die Assembly „System.Web“ ein.  
  
2.  Wählen Sie die Datei Form1 aus. Wählen Sie dann **Ansicht &#124; Code** aus dem [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Hauptmenü aus.  
  
3.  Fügen Sie oben in der Datei Form1 im Code-Editor die folgenden Statements hinzu.  
  
     [!code-csharp[ClientApplicationServices#001](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#001)]
     [!code-vb[ClientApplicationServices#001](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#001)]  
  
4.  Doppelklicken Sie im **Projektmappen-Explorer**auf Form1, um den Designer anzuzeigen.  
  
5.  Doppelklicken Sie im Designer auf die Formularoberfläche, um einen <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> Ereignishandler mit dem Namen `Form1_Load`anzulegen.  
  
     Der Code-Editor wird mit dem Cursor im `Form1_Load` -Verfahren angezeigt.  
  
6.  Fügen Sie der `Form1_Load` -Methode folgenden Code hinzu.  
  
     Dieser Code verweigert nicht authentifizierten Benutzern den Zugriff, indem er die Anwendung beendet. Alternativ könnten Sie nicht authentifizierten Benutzern den Zugriff auf das Formular gestatten, ihren zugriff auf bestimmte Funktionen hingegen verweigern. Normalerweise nehmen Sie keine Hardcodierung des Benutzernamens und des Kennwortes vor, es ist jedoch hilfreich zu Testzwecken. Im nächsten Abschnitt ersetzen Sie diesen Code durch einen robusteren Code, der ein Anmeldedialogfeld aufruft und der die Ausnahmebehandlung beinhaltet.  
  
     Beachten Sie, dass die `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> -Methode in [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)]vorhanden ist. Diese Methode delegiert die Arbeit an den konfigurierten Authentifizierungsanbieter und kehrt zurück, wenn die `true` -Authentifizierung erfolgreich war. Ihr Anwendungscode erfordert keinen direkten Verweis auf den Dienstanbieter.  
  
     [!code-csharp[ClientApplicationServices#300](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#300)]
     [!code-vb[ClientApplicationServices#300](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#300)]  
  
 Sie können jetzt F5 drücken, um die Anwendung auszuführen. Da Sie einen gültigen Benutzernamen und ein Kennwort angeben, wird das Formular angezeigt.  
  
> [!NOTE]
>  Wenn Sie die Anwendung nicht ausführen können, versuchen Sie, den ASP.NET Development Server anzuhalten. Stellen Sie beim Neustart des Servers sicher, dass der Port auf 55555 festgelegt ist.  
  
 Um stattdessen die Fehlermeldung zu sehen, ändern Sie die <xref:System.Web.Security.Membership.ValidateUser%2A> Parameter. Ersetzen Sie beispielsweise den zweiten `"manager!"` Parameter durch ein falsches Kennwort, wie `"MANAGER"`.  
  
## <a name="adding-a-login-form-as-a-credentials-provider"></a>Hinzufügen eines Anmeldeformulars als Anmeldeinformationsanbieter  
 Sie können die Benutzeranmeldeinformationen im Anwendungscode abrufen und an die <xref:System.Web.Security.Membership.ValidateUser%2A> Methode übergeben. Allerdings ist es oft hilfreich, den Anmeldeinformationen-Akquisitionscode getrennt von Ihrem Anwendungscode zu halten, für den Fall, dass Sie ihn später ändern möchten.  
  
 Im folgenden Verfahren konfigurieren Sie Ihre Anwendung auf die Verwendung eines Anmeldeinformationsanbieters. Dann ändern Sie Ihren <xref:System.Web.Security.Membership.ValidateUser%2A> Methodenaufruf zum Bestehen <xref:System.String.Empty> für beide Parameter. Die leeren Zeichenfolgen signalisieren der <xref:System.Web.Security.Membership.ValidateUser%2A> -Methode, dass sie die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> -Methode des konfigurierten Anmeldeinformationsanbieters aufrufen soll.  
  
#### <a name="to-configure-your-application-to-use-a-credentials-provider"></a>So konfigurieren Sie ihre Anwendung auf die Verwendung eines Anmeldeinformationsanbieters:  
  
1.  Wählen Sie im **Projektmappen-Explorer**das Projekt ClientAppServicesDemo aus. Wählen Sie dann im Menü **Projekt** die **ClientAppServicesDemo-Eigenschaften**aus.  
  
     Der Projekt-Designer wird angezeigt.  
  
2.  Legen Sie auf der Registerkarte **Dienste** die Option **Optional: Anmeldeinformationsanbieter** auf den folgenden Wert fest. Dieser Wert gibt den von der Assembly qualifizierten Typnamen an.  
  
    ```  
    ClientAppServicesDemo.Login, ClientAppServicesDemo  
    ```  
  
3.  Ersetzen Sie in der Codedatei Form1 den Code in der `Form1_Load` -Methode durch den folgenden Code:  
  
     Dieser Code zeigt eine Begrüßungsnachricht an. Dann ruft er die `ValidateUsingCredentialsProvider` -Methode auf, die im nächsten Schritt hinzugefügt wird. Wenn der Benutzer nicht authentifiziert ist, gibt die `ValidateUsingCredentialsProvider` -Methode `false` aus, und die Methode `Form1_Load` wird wiederhergestellt. Dadurch wird verhindert, dass durch eine Ausführung vor Anwendungsende zusätzlicher Code ausgeführt wird. Die Willkommensnachricht ist nützlich, um zu verdeutlichen, wann die Anwendung neu gestartet wird. Sie fügen Code hinzugefügt, um die Anwendung neu zu starten, wenn Sie später in dieser exemplarischen Vorgehensweise die Abmeldung implementieren.  
  
     [!code-csharp[ClientApplicationServices#011](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#011)]
     [!code-vb[ClientApplicationServices#011](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#011)]  
  
4.  Fügen Sie die folgende Methode nach der `Form1_Load` -Methode hinzu.  
  
     Diese Methode transferiert leere Zeichenfolgen an die `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> -Methode, wodurch das Anmeldedialogfeld angezeigt wird. Wenn der Authentifizierungsdienst nicht verfügbar ist, gibt die <xref:System.Web.Security.Membership.ValidateUser%2A> -Methode <xref:System.Net.WebException>aus. In diesem Fall zeigt die `ValidateUsingCredentialsProvider` -Methode eine Warnmeldung an und fragt, ob der Benutzer den Vorgang im Offline-Modus wiederholen möchte. Diese Funktionalität erfordert die Funktion **Kennworthash lokal speichern, um Offlineanmeldung zu ermöglichen** , die in [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)beschrieben wird. Dieses Feature wird standardmäßig für neue Projekte aktiviert.  
  
     Wenn der Benutzer nicht überprüft wird, zeigt die `ValidateUsingCredentialsProvider` -Methode eine Fehlermeldung an und beendet die Anwendung. Schließlich gibt diese Methode das Ergebnis des Authentifizierungsversuchs aus.  
  
     [!code-csharp[ClientApplicationServices#020](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#020)]
     [!code-vb[ClientApplicationServices#020](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#020)]  
  
### <a name="creating-a-login-form"></a>Erstellen eines Anmeldeformulars  
 Ein Anmeldeinformationsanbieter ist eine Klasse oder eine Struktur, die die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> -Schnittstelle implementiert. Diese Schnittstelle verfügt über eine einzelne Methode namens <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> , die ein <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> Objekt ausgibt. In den folgenden Verfahren wird beschrieben, wie ein Anmeldedialogfeld zu erstellen ist, das <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> implementiert, um sich selbst darzustellen und um die vom Benutzer angegebenen Anmeldeinformationen auszugeben.  
  
 Für Visual Basic und C# werden separate Verfahren angeboten, da Visual Basic eine **Anmeldeformular**-Vorlage bereitstellt. Dies spart Zeit- und Programmieraufwand.  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-visual-basic"></a>Erstellen Sie als Anmeldeinformationsanbieter ein Anmeldedialogfeld in Visual Basic  
  
1.  Wählen Sie im **Projektmappen-Explorer**das ClientAppServicesDemo-Projekt aus. Wählen Sie dann im Menü **Projekt** die Option **Hinzufügen | Neues Element**aus.  
  
2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Vorlage **Anmeldeformular** aus. Ändern Sie den Wert für **Name** in `Login.vb`, und klicken Sie dann auf **Hinzufügen**.  
  
     Das Anmeldedialogfeld wird im Windows Forms-Designer angezeigt.  
  
3.  Wählen Sie im Designer die Schaltfläche **OK** aus. Legen Sie im Fenster **Eigenschaften** `DialogResult` auf `OK`fest.  
  
4.  Fügen Sie im Designer ein `CheckBox` Steuerelement unterhalb des **Kennwort** -Textfeldes ein.  
  
5.  Geben Sie in das Fenster **Eigenschaften** einen **(Name)**-Wert von `rememberMeCheckBox` und einen **Text**-Wert von `&Remember me` ein.  
  
6.  Wählen Sie **Ansicht &#124; Code** aus [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] im Hauptmenü aus.  
  
7.  Fügen Sie im Code-Editor am oberen Rand der Datei den folgenden Code hinzu:  
  
     [!code-vb[ClientApplicationServices#101](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#101)]  
  
8.  Ändern Sie als Nächstes die Klassensignatur, sodass die Klasse die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> -Schnittstelle implementiert.  
  
     [!code-vb[ClientApplicationServices#110](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#110)]  
  
9. Stellen Sie sicher, dass sich der Cursor hinter `IClientformsAuthenticationCredentialsProvider`befindet, und drücken Sie dann die EINGABETASTE, um die `GetCredentials` -Methode zu generieren.  
  
10. Suchen Sie die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> Implementierung, und ersetzten Sie sie durch den folgenden Code.  
  
     [!code-vb[ClientApplicationServices#120](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#120)]  
  
 Die folgende C#-Prozedur enthält die gesamte Codeauflistung für ein einfaches Anmeldedialogfeld. Das Layout dieses Dialogfelds ist recht einfach gehalten, aber der wichtigste Teil ist die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> -Implementierung.  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-c"></a>So erstellen Sie als Anmeldeinformationsanbieter ein Anmeldedialogfeld in C#:  
  
1.  Wählen Sie im **Projektmappen-Explorer**das ClientAppServicesDemo-Projekt aus. Wählen Sie dann im Menü **Projekt** die Option **Klasse hinzufügen**aus.  
  
2.  Ändern Sie im Dialogfeld **Neues Element hinzufügen** den Wert für **Name** in `Login.cs`. Klicken Sie dann auf **Hinzufügen**.  
  
     Die Datei Login.cs wird im Code-Editor geöffnet.  
  
3.  Ersetzen Sie den Standardcode durch den folgenden Code.  
  
     [!code-csharp[ClientApplicationServices#200](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#200)]  
  
 Sie können die Anwendung nun ausführen. Das Anmeldedialogfeld wird angezeigt. Um diesen Code zu testen, probieren Sie verschiedene Anmeldeinformationen aus – sowohl gültige als auch ungültige – und vergewissern Sie sich, dass Sie nur mit gültigen Anmeldeinformationen auf das Formular zugreifen können. Gültige Benutzernamen sind `employee` und `manager` mit den Kennwörtern `employee!` bzw. `manager!` .  
  
> [!NOTE]
>  Wählen Sie zu diesem Zeitpunkt nicht **Anmeldedaten** aus. Ansonsten können Sie sich nicht mehr als ein anderer Benutzer anmelden, bis Sie die Abmeldung später in dieser exemplarischen Vorgehensweise implementiert haben.  
  
## <a name="adding-role-based-functionality"></a>Hinzufügen rollenbasierter Funktionalität  
 Im folgenden Verfahren müssen Sie dem Formular eine Schaltfläche hinzufügen und diese nur für Benutzer in der Managerrolle anzeigen lassen.  
  
#### <a name="to-change-the-user-interface-based-on-user-role"></a>So ändern Sie die Benutzerrollen-basierte Benutzeroberfläche:  
  
1.  Wählen Sie im **Projektmappen-Explorer** im Projekt ClientAppServicesDemo die Option Form1 aus. Wählen Sie dann **Ansicht &#124; Designer** aus [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] im Hauptmenü aus.  
  
2.  Fügen Sie im Designer dem Formular ein <xref:System.Windows.Forms.Button>-Steuerelement aus der **Toolbox** hinzu.  
  
3.  Legen Sie im Fenster **Eigenschaften** die folgenden Eigenschaften für die Schaltfläche fest:  
  
  	|Eigenschaft|Wert|  
  	|--------------|-----------|  
  	|**(Name)**|managerOnlyButton|  
  	|**Text**|&Manager-Aufgabe|  
  	|**Visible**|`False`|  
  
4.  Fügen Sie im Code-Editor am Ende des Abschnitts `Form1_Load` den folgenden Code hinzu:  
  
     Dieser Code ruft die `DisplayButtonForManagerRole` -Methode auf, die im nächsten Schritt hinzugefügt wird.  
  
     [!code-csharp[ClientApplicationServices#012](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#012)]
     [!code-vb[ClientApplicationServices#012](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#012)]  
  
5.  Fügen Sie der Formular1-Klasse die folgende Methode hinzu.  
  
     Diese Methode ruft die <xref:System.Security.Principal.IPrincipal.IsInRole%2A> -Methode von <xref:System.Security.Principal.IPrincipal> auf, die von der Eigenschaft `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> ausgegeben wurde. Für Anwendungen, die für die Verwendung von Clientanwendungsdiensten konfiguriert sind, gibt diese Eigenschaft eine(n) <xref:System.Web.ClientServices.ClientRolePrincipal>aus. Da diese Klasse die <xref:System.Security.Principal.IPrincipal> -Schnittstelle implementiert, müssen Sie nicht explizit auf diese verweisen.  
  
     Wenn sich der Benutzer in der „Manager“-Rolle befindet, dann legt die `DisplayButtonForManagerRole` -Methode die <xref:System.Windows.Forms.Control.Visible%2A> -Eigenschaft von `managerOnlyButton` auf `true`fest. Bei dieser Methode wird außerdem eine Fehlermeldung angezeigt, wenn eine <xref:System.Net.WebException> ausgelöst wird, was bedeutet, dass der Rollendienst nicht verfügbar ist.  
  
    > [!NOTE]
    >  Die <xref:System.Web.ClientServices.ClientRolePrincipal.IsInRole%2A> Methode gibt stets `false` aus, wenn die Benutzeranmeldung abgelaufen ist. Dies geschieht nicht, wenn die Anwendung die <xref:System.Security.Principal.IPrincipal.IsInRole%2A> Methode einmal kurz nach der Authentifizierung aufruft, wie im Beispielcode für diese exemplarische Vorgehensweise dargestellt. Wenn Ihre Anwendung Benutzerrollen zu anderen Zeiten abrufen muss, empfiehlt es sich, Code hinzufügen, um Benutzer, deren Anmeldung abgelaufen ist, erneut zu überprüfen. Wenn allen gültigen Benutzern Rollen zugewiesen sind, können Sie bestimmen, ob die Anmeldung, abgelaufen ist, in dem Sie die <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A?displayProperty=nameWithType> -Methode aufrufen. Wenn keine Rollen ausgegeben, ist die Anmeldung abgelaufen. Ein Beispiel für diese Funktion finden Sie unter der <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A> -Methode. Diese Funktion ist nur erforderlich, wenn Sie die Option **Verlangen, dass sich der Benutzer bei Ablauf des Cookies erneut anmelden** in der Anwendungskonfiguration ausgewählt haben. Weitere Informationen finden Sie unter [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
     [!code-csharp[ClientApplicationServices#030](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#030)]
     [!code-vb[ClientApplicationServices#030](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#030)]  
  
 Wenn die Authentifizierung erfolgreich ist, legt der Client-Authentifizierungsanbieter die <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType>-Eigenschaft auf eine Instanz der <xref:System.Web.ClientServices.ClientRolePrincipal>-Klasse fest. Diese Klasse implementiert die <xref:System.Security.Principal.IPrincipal.IsInRole%2A> -Methode, damit die Arbeit an den konfigurierten Rollenanbieter delegiert werden kann. Wie zuvor erfordert Ihr Anwendungscode keinen direkten Verweis auf den Dienstanbieter.  
  
 Sie können die Anwendung jetzt ausführen und sich als Mitarbeiter anmelden, um festzustellen, dass die Schaltfläche nicht eingeblendet wird. Dann melden Sie sich als Manager an,  um festzustellen, dass die Schaltfläche nun angezeigt wird.  
  
## <a name="accessing-web-settings"></a>Zugriff auf Webeinstellungen  
 Im folgenden Verfahren fügen Sie dem Formular ein Textfeld hinzu und binden es an eine Webeinstellung. Wie beim vorherigen Code, bei dem Authentifizierung und Rollen verwendet werden, greift der Einstellungscode nicht direkt auf den Einstellungsanbieter zu. Stattdessen wird die stark typisierte Klasse `Settings` (als `Properties.Settings.Default` in C# und `My.Settings` in Visual Basic) von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] für Ihr Projekt generiert.  
  
#### <a name="to-use-web-settings-in-your-user-interface"></a>So verwenden Sie die Webeinstellungen auf  der Benutzeroberfläche:  
  
1.  Stellen Sie durch Überprüfung des Benachrichtigungsbereichs der Taskleiste  sicher, dass der **ASP.NET Web Development Server** weiterhin ausgeführt wird. Wenn Sie den Server angehalten haben, starten Sie die Anwendung neu (wodurch automatisch der Server gestartet wird). Schließen Sie dann das Anmeldedialogfeld.  
  
2.  Wählen Sie im **Projektmappen-Explorer**das Projekt ClientAppServicesDemo aus. Wählen Sie dann im Menü **Projekt** die **ClientAppServicesDemo-Eigenschaften**aus.  
  
     Der Projekt-Designer wird angezeigt.  
  
3.  Klicken Sie auf der Registerkarte **Einstellungen** auf **Webeinstellungen laden**.  
  
     Ein Dialogfeld **Anmelden** wird angezeigt.  
  
4.  Geben Sie Anmeldeinformationen für Mitarbeiter oder Manager ein, und klicken Sie auf **Anmelden**. Die Webeinstellung, die Sie verwenden, ist nur für den Zugriff durch authentifizierte Benutzer konfiguriert. Ein Klicken auf **Anmeldung überspringen** bewirkt somit, dass keine Einstellungen geladen werden.  
  
     Die `WebSettingsTestText` Einstellung wird im Designer mit dem Standardwert `DefaultText`angezeigt. Darüber hinaus wird eine `Settings` Klasse mit einer Eigenschaft `WebSettingsTestText` für das Projekt generiert.  
  
5.  Wählen Sie im **Projektmappen-Explorer** im Projekt ClientAppServicesDemo die Option Form1 aus. Wählen Sie dann **Ansicht &#124; Designer** aus [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] im Hauptmenü aus.  
  
6.  Fügen Sie im Designer dem Formular ein <xref:System.Windows.Forms.TextBox>-Steuerelement hinzu.  
  
7.  Geben Sie im Fenster **Eigenschaften** für **(Name)** den Wert `webSettingsTestTextBox`ein.  
  
8.  Fügen Sie im Code-Editor den folgenden Code am Ende des Abschnitts `Form1_Load` hinzu:  
  
     Dieser Code ruft die `BindWebSettingsTestTextBox` -Methode auf, die im nächsten Schritt hinzugefügt wird.  
  
     [!code-csharp[ClientApplicationServices#013](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#013)]
     [!code-vb[ClientApplicationServices#013](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#013)]  
  
9. Fügen Sie der Formular1-Klasse die folgende Methode hinzu.  
  
     Diese Methode bindet die <xref:System.Windows.Forms.TextBox.Text%2A> -Eigenschaft von `webSettingsTestTextBox` an die `WebSettingsTestText` -Eigenschaft  der `Settings` -Klasse, die früher bei diesem Verfahren generiert wurde. Bei dieser Methode wird außerdem eine Fehlermeldung angezeigt, wenn <xref:System.Net.WebException> ausgelöst wird, was bedeutet, dass der Webeinstellungsdienst nicht verfügbar ist.  
  
     [!code-csharp[ClientApplicationServices#040](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#040)]
     [!code-vb[ClientApplicationServices#040](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#040)]  
  
    > [!NOTE]
    >  Sie verwenden die Datenbindung in der Regel, um die automatische bidirektionale Kommunikation zwischen einem Steuerelement und einer Webeinstellung zu aktivieren. Sie können jedoch auf Web-Einstellungen, wie im folgenden Beispiel dargestellt, auch direkt zugreifen:  
  
     [!code-csharp[ClientApplicationServices#322](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#322)]
     [!code-vb[ClientApplicationServices#322](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#322)]  
  
10. Wählen Sie im Designer das Formular aus. Klicken Sie dann im Fenster **Eigenschaften** auf die Schaltfläche **Ereignisse** .  
  
11. Wählen Sie das <xref:System.Windows.Forms.Form.FormClosing> -Ereignis aus, und drücken Sie dann die EINGABETASTE, um einen Ereignishandler zu generieren.  
  
12. Ersetzen Sie die generierte Methode durch den folgenden Code:  
  
     Der <xref:System.Windows.Forms.Form.FormClosing> -Ereignishandler ruft die `SaveSettings` -Methode ab, welche auch von der Abmeldefunktion verwendet wird, die Sie im nächsten Abschnitt hinzufügen werden. Bei der `SaveSettings` -Methode wird zunächst verifiziert, dass sich der Benutzer nicht abgemeldet hat. Dies geschieht durch die Überprüfung der <xref:System.Security.Principal.IIdentity.AuthenticationType%2A> -Eigenschaft von <xref:System.Security.Principal.IIdentity> , die vom derzeitigen Rektor zurückgegeben wurde. Der aktuelle Rektor wird über die Eigenschaft `static` <xref:System.Threading.Thread.CurrentPrincipal%2A> aufgerufen. Wenn der Benutzer für Clientanwendungsdienste authentifiziert wurde, ist der Authentifizierungstyp „ClientForms“. Die `SaveSettings` -Methode kann nicht einfach nur die <xref:System.Security.Principal.IIdentity.IsAuthenticated%2A?displayProperty=nameWithType> -Eigenschaft überprüfen, da der Benutzer nach der Abmeldung über eine gültige Windows-Identität verfügen mag.  
  
     Wenn sich der Benutzer nicht abgemeldet hat, erfasst die `SaveSettings` -Methode die <xref:System.Configuration.ApplicationSettingsBase.Save%2A> -Methode der `Settings` -Klasse, die zuvor in diesem Verfahren weiter oben in diesem Verfahren generiert wurde. Diese Methode kann eine(n) <xref:System.Net.WebException> auslösen, wenn der Authentifizierungscookie abgelaufen ist. Dies tritt nur ein, wenn Sie die Option **Verlangen, dass sich der Benutzer bei Ablauf des Cookies erneut anmelden** in der Anwendungskonfiguration ausgewählt haben. Weitere Informationen finden Sie unter [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md). Die `SaveSettings` -Methode verarbeitet den Ablauf der Cookies durch den Aufruf <xref:System.Web.Security.Membership.ValidateUser%2A> des Anmeldedialogfeldes. Wenn sich der Benutzer erfolgreich anmeldet, versucht die `SaveSettings` -Methode, die Einstellungen erneut zu speichern, indem sie sich selbst aufruft.  
  
     Wie beim vorherigen Code gibt die `SaveSettings` -Methode eine Fehlermeldung aus, wenn der Remotedienst nicht verfügbar ist. Wenn der Einstellungsanbieter nicht auf den Remotedienst zugreifen kann, werden die Einstellungen weiterhin im lokalen Cache gespeichert und erneut geladen, wenn die Anwendung neu gestartet wird.  
  
     [!code-csharp[ClientApplicationServices#050](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#050)]
     [!code-vb[ClientApplicationServices#050](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#050)]  
  
13. Fügen Sie der Formular1-Klasse die folgende Methode hinzu.  
  
     Dieser Code behandelt das <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved?displayProperty=nameWithType> -Ereignis und zeigt eine Warnung an, wenn eine oder mehrere der Einstellungen nicht gespeichert werden konnten. Das <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> -Ereignis tritt nicht ein, wenn der Einstellungsdienst nicht verfügbar ist, oder wenn der Authentifizierungscookie abgelaufen ist. Das <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> -Ereignis tritt beispielsweise ein, wenn sich ein Benutzer bereits abgemeldet hat. Sie können diesen Ereignishandler testen, indem Sie den Abmeldungscode unmittelbar vor dem Aufruf der `SaveSettings` -Methode direkt zur <xref:System.Configuration.ApplicationSettingsBase.Save%2A> -Methode hinzufügen. Der von Ihnen verwendbare Abmeldungscode ist im nächsten Abschnitt beschrieben.  
  
     [!code-csharp[ClientApplicationServices#090](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#090)]
     [!code-vb[ClientApplicationServices#090](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#090)]  
  
14. Fügen Sie bei C# den folgenden Code am Ende der `Form1_Load` -Methode hinzu. Dieser Code weist die Methode zu, die Sie im letzten Schritt mit dem <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> -Ereignis hinzugefügt haben.  
  
     [!code-csharp[ClientApplicationServices#015](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#015)]  
  
 Um die Anwendung an diesem Punkt zu testen, führen Sie sie mehrmals, sowohl als Mitarbeiter als auch als Manager aus. Geben Sie dabei unterschiedliche Werte in das Textfeld ein. Die Werte bleiben von einer Sitzung zur nächsten je nach Benutzer erhalten.  
  
## <a name="implementing-logout"></a>Implementieren der Abmeldung  
 Wenn der Benutzer bei der Anmeldung das Kontrollkästchen **Anmeldedaten** auswählt, authentifiziert die Anwendung den Benutzer bei nachfolgenden Ausführungen automatisch. Die automatische Authentifizierung wird dann fortgesetzt, während sich die Anwendung im Offline-Modus befindet, oder bis der Authentifizierungscookie abläuft. In manchen Fällen benötigen jedoch mehrere Benutzer Zugriff auf die Anwendung oder ein einzelner Benutzer muss sich gelegentlich möglicherweise mit anderen Anmeldeinformationen anmelden. Um dieses Szenario zu aktivieren, müssen Sie die Abmeldefunktion implementieren, wie im folgenden Verfahren beschrieben.  
  
#### <a name="to-implement-logout-functionality"></a>So implementieren Sie die Abmeldefunktion:  
  
1.  Fügen Sie im Form1-Designer dem Formular ein <xref:System.Windows.Forms.Button>-Steuerelement aus der **Toolbox** hinzu.  
  
2.  Geben Sie im Fenster **Eigenschaften** als **(Name)** den Wert `logoutButton` und für **Text** den Wert **&Abmelden** ein.  
  
3.  Doppelklicken Sie auf `logoutButton`, um einen <xref:System.Windows.Forms.Control.Click>-Ereignishandler zu generieren.  
  
     Der Code-Editor wird mit dem Cursor im `logoutButton_Click` -Verfahren angezeigt.  
  
4.  Ersetzen Sie die `logoutButton_Click` -Methode durch folgenden Code:  
  
     Dieser Ereignishandler ruft zuerst die `SaveSettings` -Methode auf, die Sie im vorherigen Abschnitt hinzugefügt haben. Anschließend ruft der Ereignishandler die <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A?displayProperty=nameWithType> -Methode auf. Wenn der Authentifizierungsdienst nicht verfügbar ist, gibt die <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A> -Methode <xref:System.Net.WebException>aus. In diesem Fall die `logoutButton_Click` Methode zeigt eine Warnmeldung an und wechselt vorübergehend in den Offline-Modus, um den Benutzer abzumelden. Der Offline-Modus wird im nächsten Abschnitt beschrieben.  
  
     Beim Abmelden wird der lokale Authentifizierungscookie gelöscht, sodass beim Neustart der Anwendung eine Anmeldung erforderlich ist. Nach der Abmeldung startet der Ereignishandler die Anwendung neu. Wenn die Anwendung neu gestartet wird, wird die Begrüßungsnachricht, gefolgt vom Dialogfeld „Anmelden“ angezeigt. Die Begrüßungsnachricht verdeutlicht, dass die Anwendung neu gestartet wurde. Dadurch wird eine mögliche Verwirrung vermieden, wenn sich der Benutzer anmelden muss, um die Einstellungen zu speichern, und sich dann erneut anmelden muss, weil die Anwendung neu gestartet wurde.  
  
     [!code-csharp[ClientApplicationServices#070](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#070)]
     [!code-vb[ClientApplicationServices#070](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#070)]  
  
 Um die Abmeldefunktionalität zu testen, führen Sie die Anwendung aus, und wählen Sie **Anmeldedaten** aus dem Dialogfeld „Anmelden“ aus. Als Nächstes schließen Sie die Anwendung und starten Sie sie neu, um zu verifizieren, dass Sie sich nicht mehr anmelden müssen. Schließlich starten Sie die Anwendung durch Klicken auf Abmelden.  
  
## <a name="enabling-offline-mode"></a>Aktivieren des Offline-Modus  
 Im folgenden Verfahren fügen Sie dem Formular ein Kontrollkästchen hinzu, um den Benutzer den Wechsel in den Offline-Modus zu ermöglichen. Die Anwendung zeigt den Offline-Modus an, indem die `static` <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A?displayProperty=nameWithType> -Eigenschaft auf `true`festgelegt wird. Der Offline-Status wird auf der lokalen Festplatte an dem Speicherort gespeichert, den die <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> -Eigenschaft angibt. Dies bedeutet, dass der Offline-Status je nach Benutzer und Anwendung gespeichert wird.  
  
 Im Offline-Modus werden bei allen Kundenanwendungsdienst-Anforderungen Daten aus dem lokalen Cache abgerufen, statt zu versuchen, ob die Dienste zuzugreifen In der Standardkonfiguration enthalten die lokalen Daten das Benutzerkennwort in verschlüsselter Form. Dadurch kann sich der Benutzer anmelden, während sich die Anwendung im Offline-Modus befindet. Weitere Informationen finden Sie unter [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
#### <a name="to-enable-offline-mode-in-your-application"></a>So wird der Offline-Modus in der Anwendung aktiviert:  
  
1.  Wählen Sie im **Projektmappen-Explorer** im Projekt ClientAppServicesDemo die Option Form1 aus. Wählen Sie dann **Ansicht &#124; Designer** aus [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] im Hauptmenü aus.  
  
2.  Fügen Sie im Designer dem Formular ein <xref:System.Windows.Forms.CheckBox>-Steuerelement hinzu.  
  
3.  Geben Sie im Fenster **Eigenschaften** als **(Name)** den Wert `workOfflineCheckBox` und als **Text** den Wert **&Offline arbeiten** ein.  
  
4.  Klicken Sie im Fenster **Eigenschaften** auf die Schaltfläche **Ereignisse** .  
  
5.  Wählen Sie das <xref:System.Windows.Forms.CheckBox.CheckedChanged> -Ereignis aus, und drücken Sie dann die EINGABETASTE, um einen Ereignishandler zu generieren.  
  
6.  Ersetzen Sie die generierte Methode durch den folgenden Code:  
  
     Dieser Code aktualisiert den <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A> Wert und validiert den Benutzer, wenn dieser wieder in den Online-Modus wechselt, im Hintergrund neu. Bei der <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A?displayProperty=nameWithType> -Methode werden die zwischengespeicherten Anmeldeinformationen verwendet, sodass sich der Benutzer nicht explizit neu anmelden muss. Wenn der Authentifizierungsdienst nicht verfügbar ist, wird eine Warnmeldung angezeigt, und die Anwendung bleibt offline.  
  
    > [!NOTE]
    >  Die <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A> -Methode wird nur ergänzend bereitgestellt. Da sie nicht über einen Rückgabewert verfügt, kann sie nicht angeben, ob die erneute Überprüfung fehlgeschlagen ist. Die erneute Überprüfung kann z. B. fehlschlagen, wenn die Anmeldeinformationen des Benutzers auf dem Server geändert wurden. In diesem Fall ist es ratsam, Code einzuschließen, der die Benutzer nach dem Fehlschlagen eines Dienstaufrufs explizit validiert. Weitere Informationen finden Sie im Abschnitt Zugriff auf Webeinstellungen weiter oben in dieser exemplarischen Vorgehensweise.  
  
     Nach der erneuten Validierung speichert dieser Code alle Änderungen an den lokalen Webeinstellungen durch Aufrufen der `SaveSettings` -Methode, die Sie zuvor hinzugefügt haben. Dann werden alle neuen Werte auf dem Server durch Aufrufen der Methode <xref:System.Configuration.ApplicationSettingsBase.Reload%2A> der Klasse `Settings` (als `Properties.Settings.Default` in C# und `My.Settings` in Visual Basic) des Projekts abgerufen.  
  
     [!code-csharp[ClientApplicationServices#080](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#080)]
     [!code-vb[ClientApplicationServices#080](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#080)]  
  
7.  Fügen Sie den folgenden Code am Ende der `Form1_Load` -Methode ein, um sicherzustellen, dass das Kontrollkästchen den aktuellen Verbindungsstatus anzeigt.  
  
     [!code-csharp[ClientApplicationServices#014](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#014)]
     [!code-vb[ClientApplicationServices#014](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#014)]  
  
 Dadurch ist die exemplarische Anwendung abgeschlossen. Um den Offlinebetrieb zu testen, führen Sie die Anwendung aus. Melden Sie sich als Mitarbeiter oder Manager an, und wählen Sie dann **Offline arbeiten**aus. Ändern Sie den Wert im Textfeld, und schließen Sie die Anwendung. Starten Sie die Anwendung neu. Bevor Sie sich anmelden, klicken Sie im Infobereich der Taskleiste mit der rechten Maustaste auf ASP.NET Development Server. Klicken Sie dann auf **Stopp**. Melden Sie sich dann wie üblich an. Selbst wenn der Server nicht ausgeführt wird, können Sie sich dennoch anmelden. Ändern Sie den Wert im Textfeld, beenden Sie den Server und starten Sie ihn neu, um den geänderten Wert anzuzeigen.  
  
## <a name="summary"></a>Zusammenfassung  
 In dieser exemplarischen Vorgehensweise haben Sie gelernt, Clientanwendungsdiensten in einer Windows Forms-Anwendung zu aktivieren und zu verwenden. Nach dem Einrichten eines Testservers haben Sie Ihrer Anwendung Code hinzugefügt, um die Benutzer zu authentifizieren und die Benutzerrollen und Anwendungseinstellungen vom Server abzurufen. Außerdem haben Sie gelernt, den Offlinemodus zu aktivieren, sodass Ihre Anwendung anstelle von Remotediensten einen lokalen Datencache verwendet, wenn keine Verbindung verfügbar ist.  
  
## <a name="next-steps"></a>Nächste Schritte  
 In einer realen Anwendung werden Sie für viele Benutzer auf Daten von einem Remoteserver zugreifen, der möglicherweise nicht immer verfügbar ist bzw. der ohne Vorwarnung ausfallen kann. Um die Anwendung robuster machen, müssen Sie angemessen auf Situationen reagieren, in denen der Dienst nicht verfügbar ist. Diese exemplarische Vorgehensweise umfasst Try/Catch-Blöcke zum Abfangen von <xref:System.Net.WebException> und zum Anzeigen einer Fehlermeldung, wenn der Dienst nicht verfügbar ist. Im Produktionscode empfiehlt es sich, in diesem Fall den Wechsel in den Offline-Modus, das Beenden der Anwendung oder die Verweigerung des Zugriffs auf bestimmte Funktionen zu erwägen.  
  
 Zur Erhöhung der Sicherheit Ihrer Anwendung stellen Sie sicher, dass Anwendung und Server vor der Bereitstellung gründlich getestet wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [Übersicht über Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [Vorgehensweise: Konfigurieren von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [ASP.NET-Websiteverwaltungs-Tool](http://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec)  
 [Erstellen und Konfigurieren der Datenbank für die Anwendungsdienste für SQL Server](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)  
 [Exemplarische Vorgehensweise: Verwenden von ASP.NET-Anwendungsdiensten](http://msdn.microsoft.com/library/f3f394f0-20d6-4361-aa8f-4b21bf4933eb)
