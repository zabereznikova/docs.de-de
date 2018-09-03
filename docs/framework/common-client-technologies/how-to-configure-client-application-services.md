---
title: 'Gewusst wie: Konfigurieren von Clientanwendungsdiensten'
ms.date: 03/30/2017
helpviewer_keywords:
- client application services, configuring
ms.assetid: 34a8688a-a32c-40d3-94be-c8e610c6a4e8
ms.openlocfilehash: a65c216397f240b77eb81f88d8f2a2da122e1ccf
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43399237"
---
# <a name="how-to-configure-client-application-services"></a>Gewusst wie: Konfigurieren von Clientanwendungsdiensten
In diesem Thema wird beschrieben, wie Sie den Visual Studio-**Projekt-Designer** zum Aktivieren und Konfigurieren von Clientanwendungsdiensten verwenden. Sie können Clientanwendungsdienste verwenden, um Benutzer zu überprüfen sowie um Benutzerrollen und Einstellungen von einem vorhandenen [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]-Anwendungsdienst abzurufen. Nach der Konfiguration können Sie auf die aktivierten Dienste im Anwendungscode zugreifen, wie unter [Übersicht über Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services-overview.md) beschrieben. Weitere Informationen zu den [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]-Anwendungsdiensten finden Sie unter [Übersicht über ASP.NET-Anwendungsdienste](https://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).  
  
 Sie können die Clientanwendungsdienste auf der Seite **Dienste** im **Projekt-Designer** aktivieren und konfigurieren. Die Seite **Dienste** aktualisiert die Werte in der Datei „App.config“ des Projekts. Verwenden Sie den Befehl **Eigenschaften** im Menü **Projekt**, um den **Projekt-Designer** zu öffnen. Weitere Informationen zur Seite **Dienste** finden Sie unter [Services-Seite, Projekt-Designer](https://msdn.microsoft.com/library/bb398109).  
  
 Das folgende Verfahren beschreibt die grundlegende Konfiguration für Clientanwendungsdienste. Erweiterte Konfigurationsoptionen werden in späteren Abschnitten beschrieben.  
  
### <a name="to-configure-client-application-services"></a>So konfigurieren Sie Clientanwendungsdienste  
  
1.  Wählen Sie im **Projektmappen-Explorer** einen Projektknoten aus und klicken Sie dann im Menü **Projekt** auf **Eigenschaften**.  
  
     Der **Projekt-Designer** wird angezeigt.  
  
2.  Klicken Sie auf die Registerkarte **Dienste**. Die Seite **Dienste** wird angezeigt, wie in der folgenden Abbildung dargestellt.  
  
     ![Die Registerkarte „Dienste“ im Projekt-Designer](../../../docs/framework/common-client-technologies/media/casdesigner.png "casdesigner")  
  
3.  Wählen Sie auf der Seite **Dienste** die Option **Clientanwendungsdienste aktivieren**.  
  
    > [!NOTE]
    >  Clientanwendungsdienste erfordern die Vollversion von .NET Framework und werden im .NET Framework Client Profile nicht unterstützt. Wenn das Kontrollkästchen **Clientanwendungsdienste aktivieren** deaktiviert ist, stellen Sie sicher, dass als **Zielframework** das .NET Framework 3.5 oder höher festgelegt ist. Um die Einstellung **Zielframework** in C# anzuzeigen, öffnen Sie den Projekt-Designer, und klicken Sie dann auf die Seite **Anwendung**. Um die Einstellung **Zielframework** in Visual Basic anzuzeigen, öffnen Sie den Projekt-Designer, klicken Sie auf die Seite **Kompilieren** und dann auf **Erweiterte Kompilierungsoptionen**.  
  
4.  Wählen Sie **Formularauthentifizierung verwenden**, wenn Sie Ihre eigenen Anmeldesteuerelemente oder ein eigenes Dialogfeld bereitstellen möchten, oder wählen Sie **Windows-Authentifizierung verwenden**, um die vom Betriebssystem bereitgestellte Identität zu verwenden. Weitere Informationen finden Sie unter [Übersicht über Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services-overview.md).  
  
    > [!NOTE]
    >  Bei Auswahl von **Windows-Authentifizierung verwenden** werden Clientanwendungsdienste automatisch konfiguriert, sodass sie eine SQL Server Compact-Datenbank verwenden. Dies wird im Dialogfeld **Erweiterte Einstellungen für Dienste** angegeben, wie im nächsten Abschnitt beschrieben. Wenn Sie dann **Formularauthentifizierung verwenden** auswählen, wird die Einstellung **Benutzerdefinierte Verbindungszeichenfolge verwenden** nicht automatisch gelöscht. Dies kann zu Fehlern führen, wenn die [!INCLUDE[ssEW](../../../includes/ssew-md.md)]-Datenbank bereits für die Verwendung mit Windows-Authentifizierung generiert wurde. Um diese Fehler zu beheben, deaktivieren Sie die Einstellung **Benutzerdefinierte Verbindungszeichenfolge verwenden** im Dialogfeld **Erweiterte Einstellungen für Dienste**.  
  
5.  Bei Auswahl von **Formularauthentifizierung verwenden** geben Sie im Feld **Speicherort des Authentifizierungsdiensts** die URL des Diensthosts ohne den Dateinamen an. Der Designer fügt den Standarddateinamen (Authentication_JSON_AppService.axd) automatisch an, wenn der Wert in die Konfigurationsdatei geschrieben wird.  
  
6.  Wenn Sie **Formularauthentifizierung verwenden** ausgewählt haben, können Sie optional einen Wert im Feld **Anmeldeinformationsanbieter** angeben. Der Anmeldeinformationsanbieter muss die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>-Schnittstelle implementieren. Durch Verwenden eines Anmeldeinformationsanbieters können Sie die Anmeldebenutzeroberfläche vom übrigen Anwendungscode trennen. Dadurch können Sie ein einzelnes Anmeldedialogfeld erstellen, das in mehreren Anwendungen verwendet wird. Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren einer Benutzeranmeldung mit Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md).  
  
     Wenn Sie einen Anmeldeinformationsanbieter angeben, müssen Sie ihn als einen von der Assembly qualifizierten Typnamen angeben. Weitere Informationen finden Sie unter <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> und [Assemblynamen](../../../docs/framework/app-domains/assembly-names.md). In seiner einfachsten Form sieht ein von der Assembly qualifizierter Typname wie im folgenden Beispiel aus:  
  
    ```  
    MyNamespace.MyLoginClass, MyAssembly  
    ```  
  
7.  In den Feldern **Speicherort des Rollendiensts** und **Speicherort des Webeinstellungsdiensts** geben Sie den Speicherort für jeden Dienst ohne den Dateinamen an. Der Designer fügt die Standarddateinamen (Role_JSON_AppService.axd und Profile_JSON_AppService.axd) automatisch an, wenn der Wert in die Konfigurationsdatei geschrieben wird.  
  
8.  Klicken Sie optional auf **Erweitert**, um die erweiterten Einstellungen zu ändern, z. B. das Verhalten bei der lokalen Zwischenspeicherung. Weitere Informationen finden Sie in der nächsten Verfahrensbeschreibung.  
  
## <a name="advanced-configuration"></a>Erweiterte Konfiguration  
 Die folgenden Verfahren beschreiben, wie Sie Clientanwendungsdienste für weniger häufig vorkommende Szenarien konfigurieren. Beispielsweise können Sie diese Konfigurationsoptionen für Anwendungen verwenden, die an öffentlichen Speicherorten bereitgestellt werden, oder um eine verschlüsselte SQL Server Compact-Datenbank als Cache für die lokalen Daten zu verwenden.  
  
#### <a name="to-configure-advanced-settings-for-client-application-services"></a>So konfigurieren Sie erweiterte Einstellungen für Clientanwendungsdienste  
  
1.  Klicken Sie im **Projekt-Designer** auf der Seite **Dienste** auf **Erweitert**.  
  
     Das Dialogfeld **Erweiterte Einstellungen für Dienste** wird angezeigt, wie in der folgenden Abbildung dargestellt. Weitere Informationen zu diesem Dialogfeld finden Sie unter [Dialogfeld „Erweiterte Einstellungen für Dienste“](/visualstudio/ide/reference/advanced-settings-for-services-dialog-box).  
  
     ![Dialogfeld „Erweiterte Einstellungen für Dienste“](../../../docs/framework/common-client-technologies/media/casdialog.png "casdialog")  
  
2.  Aktivieren oder deaktivieren Sie **Kennworthash lokal speichern, um Offlineanmeldung zu ermöglichen**. Wenn Sie diese Option auswählen, wird das Benutzerkennwort in verschlüsselter Form lokal zwischengespeichert. Dies ist nützlich, wenn Sie den Offlinemodus für die Anwendung implementieren. Bei ausgewählter Option können Sie die Benutzer überprüfen, selbst wenn die Eigenschaft <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A> auf `true` gesetzt wurde.  
  
3.  Aktivieren oder deaktivieren Sie **Erneute Benutzeranmeldung bei Ablauf des Cookies anfordern**. Das Authentifizierungscookie ist für den Remotedienst konfiguriert und gibt an, wie lange eine Benutzeranmeldung aktiv bleibt. Weitere Informationen zum Konfigurieren des Cookies finden Sie im Abschnitt zum `timeout`-Attribut im [forms-Element für Authentifizierung (ASP.NET-Einstellungsschema)](https://msdn.microsoft.com/library/8163b8b5-ea6c-46c8-b5a9-c4c3de31c0b3).  
  
     Bei ausgewählter Option wird beim Versuch, auf die Remoterollen oder Webeinstellungsdienste zuzugreifen, eine <xref:System.Net.WebException> ausgelöst, nachdem das Authentifizierungscookie abgelaufen ist. Sie können diese Ausnahme behandeln und ein Anmeldedialogfeld anzeigen, um Benutzer erneut zu überprüfen. Ein Beispiel für dieses Verhalten finden Sie unter [Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md). Diese Option ist nützlich für Anwendungen, die an öffentlichen Speicherorten bereitgestellt werden, um sicherzustellen, dass Benutzer, die die Anwendung nach Gebrauch weiterhin ausführen, nicht auf unbestimmte Zeit authentifiziert bleiben.  
  
     Wenn Sie diese Option deaktivieren und versuchen, auf die Remotedienste zuzugreifen, nachdem das Authentifizierungscookie abgelaufen ist, werden Benutzer automatisch neu überprüft.  
  
4.  Geben Sie einen Wert für **Cachetimeout des Rollendiensts** an. Legen Sie dieses Zeitintervall auf einen kleinen Wert fest, wenn Rollen häufig aktualisiert werden, oder auf einen höheren Wert, wenn Rollen seltener aktualisiert werden. Wenn Sie den Offlinemodus implementieren, legen Sie das Zeitintervall auf einen hohen Wert, um zu verhindern, dass die Rolleninformationen ablaufen, während die Anwendung offline ist.  
  
     Der Rollenanbieter greift auf die zwischengespeicherten Rollenwerte oder den Rollendienst zu, wenn Sie die <xref:System.Web.Security.RolePrincipal.IsInRole%2A>-Methode aufrufen. Um den Cache programmgesteuert zurückzusetzen und einen Zugriff auf den Remotedienst durch diese Methode zu erzwingen, rufen Sie die <xref:System.Web.ClientServices.Providers.ClientRoleProvider.ResetCache%2A>-Methode auf.  
  
5.  Aktivieren oder deaktivieren Sie **Benutzerdefinierte Verbindungszeichenfolge verwenden**. Weitere Informationen finden Sie in der nächsten Verfahrensbeschreibung.  
  
#### <a name="to-configure-client-application-services-to-use-a-database-for-the-local-cache"></a>So konfigurieren Sie die Clientanwendungsdienste, um eine Datenbank für den lokalen Cache zu verwenden  
  
1.  Klicken Sie im **Projekt-Designer** auf der Seite **Dienste** auf **Erweitert**.  
  
     Das Dialogfeld **Erweiterte Einstellungen für Dienste** wird angezeigt.  
  
2.  Wählen Sie **Benutzerdefinierte Verbindungszeichenfolge verwenden**.  
  
     Der Standardwert von `Data Source = |SQL/CE|` wird im Textfeld angezeigt.  
  
3.  Behalten Sie den Standardwert für die Verbindungszeichenfolge bei, um eine SQL Server Compact-Datenbank zu generieren und zu verwenden. Visual Studio generiert eine Datenbankdatei und speichert sie im Verzeichnis, das von der <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType>-Eigenschaft angegeben wird.  
  
4.  Fügen Sie zum Generieren und Verwenden einer verschlüsselten [!INCLUDE[ssEW](../../../includes/ssew-md.md)]-Datenbank der Verbindungszeichenfolge die Werte `password` und `encrypt database` hinzu, wie im folgenden Beispiel gezeigt.  
  
    > [!NOTE]
    >  Achten Sie darauf, dass Sie ein sicheres Kennwort angeben. Sie können das Kennwort nicht mehr ändern, nachdem die Datenbank generiert wurde.  
  
    ```  
    Data Source = |SQL/CE|;password=<password>;encrypt database=true  
    ```  
  
5.  Geben Sie Ihre eigene Verbindungszeichenfolge an, um Ihre eigene SQL Server-Datenbank zu verwenden. Informationen über gültige Verbindungszeichenfolgenformate finden Sie in der SQL Server-Dokumentation. Diese Datenbank wird nicht automatisch generiert. Die Verbindungszeichenfolge muss auf eine vorhandene Datenbank verweisen, die Sie mit den folgenden SQL-Anweisungen erstellen können.  
  
    ```  
    CREATE TABLE ApplicationProperties (PropertyName nvarchar(256),  
        PropertyValue nvarchar(256))  
    CREATE TABLE UserProperties (PropertyName nvarchar(256),  
        PropertyValue nvarchar(256))  
    CREATE TABLE Roles (UserName nvarchar(256),   
        RoleName nvarchar(256))  
    CREATE TABLE Settings (PropertyName nvarchar(256),   
        PropertyStoredAs nvarchar(1), PropertyValue nvarchar(2048))  
    ```  
  
## <a name="using-custom-providers"></a>Verwenden von benutzerdefinierten Anbietern  
 Die Clientanwendungsdienste-Funktion verwendet standardmäßig die Anbieter im <xref:System.Web.ClientServices.Providers?displayProperty=nameWithType>-Namespace. Wenn Sie die Anwendung mithilfe der Seite **Dienste** im **Projekt-Designer** konfigurieren, werden der Datei „App.config“ Verweise auf diese Anbieter hinzugefügt. Diese Standardanbieter greifen auf entsprechende Anbieter auf dem Server zu. Webdienste werden häufig so konfiguriert, dass sie über Anbieter, wie z. B. <xref:System.Web.Security.SqlMembershipProvider> und <xref:System.Web.Security.SqlRoleProvider>, auf Benutzerdaten zugreifen.  
  
 Wenn Sie benutzerdefinierte Dienstanbieter verwenden möchten, ändern Sie normalerweise die Anbieter auf Serverseite, sodass sie für alle Clientanwendungen gelten, die auf den Server zugreifen. Sie haben allerdings die Möglichkeit, nicht standardmäßige Anbieter auf Clientseite zu verwenden. Sie können benutzerdefinierte Authentifizierungs- oder Rollenanbieter in der Datei "App.config" des Projekts angeben, wie im folgenden Verfahren gezeigt. Informationen zum Erstellen von benutzerdefinierten Authentifizierungs- und Rollenanbietern finden Sie unter [Implementieren eines Mitgliedschaftsanbieters](https://msdn.microsoft.com/library/d8658b8e-c962-4f64-95e1-4acce35e4582) und [Implementieren eines Rollenanbieters](https://msdn.microsoft.com/library/851671ce-bf9b-43f2-aba4-bc9d28b11c7d). Sie können auch einen benutzerdefinierten Einstellungsanbieter verwenden, indem Sie die `Settings`-Klasse (Zugriff als `Properties.Settings.Default` in C# und als `My.Settings` in Visual Basic) in Ihrem Projekt ändern. Weitere Informationen finden Sie unter [Architektur der Anwendungseinstellungen](../../../docs/framework/winforms/advanced/application-settings-architecture.md).  
  
#### <a name="to-configure-client-application-services-to-use-non-default-providers"></a>So konfigurieren Sie Clientanwendungsdienste, um nicht standardmäßige Anbieter zu verwenden  
  
1.  Um einen nicht standardmäßigen Authentifizierungs- oder Rollendienstanbieter zu verwenden, führen Sie zuerst alle übrigen Konfigurationseinstellungen mithilfe der Seite **Dienste** durch.  
  
2.  Schließen Sie den **Projekt-Designer**. Das ist erforderlich, da die Seite **Dienste** die Datei „App.config“ automatisch aktualisiert, auch wenn Sie keine Einstellungen ändern. Wenn Sie die Datei „App.config“, wie in diesem Verfahren beschrieben, manuell ändern und dann wieder zur Seite **Dienste** zurückkehren, werden die Änderungen zurückgesetzt.  
  
3.  Doppelklicken Sie im **Projektmappen-Explorer** auf die Datei „App.config“.  
  
     Die Anwendungskonfigurationsdatei wird im Texteditor geöffnet.  
  
4.  Gehen Sie zum `<providers>`-Element innerhalb des `<membership>`- oder `<roleManager>`-Elements. Diese Elemente sind untergeordnete Elemente des `<system.web>`-Elements. Das `<membership>`-Element wird verwendet, um den Authentifizierungsanbieter anzugeben, und das `<roleManager>`-Element wird zur Angabe von Rollenanbietern verwendet.  
  
5.  Fügen Sie ein `<add>`-Element als untergeordnetes Element des `<providers>`-Elements hinzu. Sie müssen die `name`- und `type`-Attribute wie im folgenden Beispiel gezeigt festlegen. Der `type`-Attributswert muss ein von einer Assembly qualifizierter Typname sein. Weitere Informationen finden Sie unter <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> und [Assemblynamen](../../../docs/framework/app-domains/assembly-names.md).  
  
    ```xml  
    <add name="MyCustomRoleProvider" type="MyNamespace.MyRoleProvider, MyAssembly" />  
    ```  
  
6.  Ändern Sie das `defaultProvider`-Attribut des `<membership>`- oder des `<roleManager>`-Elements, um den Namenswert aus dem `<add>`-Element anzugeben, das Sie im vorherigen Schritt hinzugefügt haben.  
  
    ```xml  
    <roleManager enabled="true" defaultProvider="MyCustomRoleProvider">  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [Übersicht über Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [Seite „Services“, Projekt-Designer](https://msdn.microsoft.com/library/bb398109)  
 [Dialogfeld „Erweiterte Einstellungen für Dienste“](/visualstudio/ide/reference/advanced-settings-for-services-dialog-box)  
 [Gewusst wie: Implementieren einer Benutzeranmeldung mit Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 [Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 [Implementieren eines ](https://msdn.microsoft.com/library/d8658b8e-c962-4f64-95e1-4acce35e4582)  
 [Implementieren eines Rollenanbieters](https://msdn.microsoft.com/library/851671ce-bf9b-43f2-aba4-bc9d28b11c7d)  
 [Architektur der Anwendungseinstellungen](../../../docs/framework/winforms/advanced/application-settings-architecture.md)  
 [Erstellen und Konfigurieren der Datenbank für die Anwendungsdienste für SQL Server](https://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)
