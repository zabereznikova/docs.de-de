---
title: Übersicht über die Sicherheit in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- code access security [Windows Forms], Windows Forms
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms], about security
- access control [Windows Forms], Windows Forms
ms.assetid: 4810dc9f-ea23-4ce1-8ea1-657f0ff1d820
ms.openlocfilehash: 36d38756f7df88ec04aca781525f0f6b0a48b768
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48839130"
---
# <a name="security-in-windows-forms-overview"></a>Übersicht über die Sicherheit in Windows Forms
Bevor [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] freigegeben wurde, hatte jeglicher Code, der auf dem Computer eines Benutzers ausgeführt wurde, dieselben Berechtigungen für Zugriffe auf Ressourcen, wie der Benutzer auf dem Computer hatte. Wenn der Benutzer beispielsweise berechtigt war, auf das Dateisystem zuzugreifen, war auch der Code berechtigt, auf das Dateisystem zuzugreifen. Wenn der Benutzer Zugriffsrechte für eine Datenbank hatte, konnte der Code ebenfalls auf diese Datenbank zugreifen. Diese Berechtigungen können für Code in ausführbaren Dateien akzeptabel sein, die der Benutzer explizit auf dem lokalen Computer installiert hat. Sie sind aber wahrscheinlich nicht für potenzielle Schadsoftware akzeptabel, der aus dem Internet oder einem lokalen Intranet stammt. Dieser Code darf nicht ohne Berechtigung auf Computerressourcen des Benutzers zugreifen können.  
  
 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] stellt eine als Codezugriffssicherheit bezeichnete Infrastruktur bereit, die es Ihnen ermöglicht, zwischen den Berechtigungen, die Code hat, und den Berechtigungen zu unterscheiden, die der Benutzer hat. Standardmäßig kann Code, der aus dem Internet oder dem Intranet stammt, nur in der Umgebung ausgeführt werden, die als teilweise vertrauenswürdige Umgebung bezeichnet wird. Teilweise Vertrauenswürdigkeit bedingt für eine Anwendung eine Reihe von Beschränkungen: Neben anderen Aspekten kann eine Anwendung weder auf die lokale Festplatte zugreifen noch nicht verwalteten Code ausführen. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] steuert anhand der Identität dieses Codes, auf welche Ressourcen er zugreifen darf: Woher stammt der Code, hat er [Assemblys mit starken Namen](../../../docs/framework/app-domains/strong-named-assemblies.md), ist er mit einem Zertifikat signiert usw.  
  
 Die [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]-Technologie, mit der Sie Windows Forms-Anwendungen bereitstellen, erleichtert Ihnen das Entwickeln von Anwendungen, die mit teilweiser Vertrauenswürdigkeit, voller Vertrauenswürdigkeit oder teilweiser Vertrauenswürdigkeit mit erweiterten Berechtigungen ausgeführt werden. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] bietet Funktionalität wie Berechtigungserweiterung und Bereitstellung vertrauenswürdiger Anwendungen, sodass Ihre Anwendung bei Bedarf volle Vertrauenswürdigkeit bzw. erweiterte Berechtigungen vom lokalen Benutzer anfordern kann.  
  
## <a name="understanding-security-in-the-net-framework"></a>Grundlegendes zur Sicherheit in .NET Framework  
 Mithilfe der Codezugriffssicherheit können für Code anhand seines Ursprungs und weiterer Aspekte seiner Identität verschiedene Vertrauensebenen festgelegt werden. Weitere Informationen zu den Beweisen, die Common Language Runtime zum Ermitteln der Sicherheitsrichtlinien verwendet, finden Sie unter [Beweis](https://msdn.microsoft.com/library/64ceb7c8-a0b4-46c4-97dc-6c22da0539da). Sie unterstützt dabei, Computersysteme vor Schadsoftware zu schützen, und sie schützt vertrauenswürdigen Code davor, absichtlich oder versehentlich die Sicherheit zu gefährden. Codezugriffssicherheit gibt Ihnen außerdem mehr Kontrolle über die Aktionen, die Ihre Anwendung ausführen kann, weil Sie die Möglichkeit haben, nur die Berechtigungen anzugeben, die für die Anwendung benötigt werden. Codezugriffssicherheit betrifft den gesamten verwalteten Code, der auf der Common Language Runtime aufsetzt, selbst wenn dieser Code keine einzige Berechtigungsüberprüfung für Codezugriffssicherheit ausführt. Weitere Informationen zur Sicherheit in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] finden Sie unter [Schlüsselbegriffe der Sicherheit](../../../docs/standard/security/key-security-concepts.md) und [Grundlagen der Codezugriffssicherheit](../../../docs/framework/misc/code-access-security-basics.md).  
  
 Wenn der Benutzer eine ausführbare Windows Forms-Datei direkt aus einem Webserver oder über eine Dateifreigabe ausführt, hängt der Grad der Vertrauenswürdigkeit, die Ihrer Anwendung gewährt wird, davon ab, wo sich der Code befindet und wie er gestartet wurde. Wenn eine Anwendung ausgeführt wird, wird sie automatisch ausgewertet, und erhält sie einen benannten Berechtigungssatz von der Common Language Runtime. Standardmäßig wird Code vom lokalen Computer der Berechtigungssatz "Voll vertrauenswürdig", Code aus einem lokalen Netzwerk der Berechtigungssatz "Lokales Intranet" und Code aus dem Internet der Berechtigungssatz "Internet" gewährt.  
  
> [!NOTE]
>  In [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 1.0 Service Pack 1 und Service Pack 2 wird der Internetzonen-Codegruppe der Berechtigungssatz "Nichts" gewährt. In allen anderen Versionen von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] wird der Internetzonen-Codegruppe der Berechtigungssatz "Internet" gewährt.  
>   
>  Die Standardberechtigungen, die in jedem dieser Berechtigungssätze gewährt werden, werden im Thema [Standardmäßige Sicherheitsrichtlinie](https://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55) aufgeführt. Abhängig von den Berechtigungen, die eine Anwendung erhält, wird sie ordnungsgemäß ausgeführt oder wird eine Sicherheitsausnahme ausgelöst.  
>   
>  Viele Windows Forms-Anwendungen werden mit [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] bereitgestellt. Für die Tools, die zum Generieren einer [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]-Bereitstellung verwendet werden, gelten andere Sicherheitsstandardwerte als die bereits erläuterten. Weitere Informationen finden Sie im folgenden Abschnitt.  
  
 Die tatsächlichen Berechtigungen, die Ihrer Anwendung gewährt werden, können sich von den Standardwerten unterscheiden, weil die Sicherheitsrichtlinie geändert werden kann. Dies kann dazu führen, dass Ihre Anwendung auf einem Computer Berechtigung hat, auf einem anderen jedoch nicht.  
  
## <a name="developing-a-more-secure-windows-forms-application"></a>Entwickeln einer sichereren Windows Forms-Anwendung  
 Sicherheit ist bei allen Schritten der Entwicklung von Anwendungen wichtig. Beginnen Sie, indem Sie die [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md) lesen.  
  
 Legen Sie dann fest, ob Ihre Anwendung mit voller Vertrauenswürdigkeit ausgeführt werden muss oder ob sie mit teilweiser Vertrauenswürdigkeit ausgeführt werden soll. Ein Ausführen Ihrer Anwendung mit voller Vertrauenswürdigkeit erleichtert den Zugriff auf Ressourcen auf dem lokalen Computer, setzt Ihre Anwendung und deren Benutzer aber hohen Sicherheitsrisiken aus, sofern Sie die Anwendung nicht genau entsprechend dem Thema "Richtlinien für das Schreiben von sicherem Code" entworfen und entwickelt haben. Ein Ausführen Ihrer Anwendung mit teilweiser Vertrauenswürdigkeit erleichtert es, eine sicherere Anwendung zu entwickeln, und verringert großenteils das Risiko, erfordert jedoch mehr Planung, wie bestimmte Features zu implementieren sind.  
  
 Wenn Sie teilweise Vertrauenswürdigkeit wählen (also entweder den Berechtigungssatz "Internet" oder "Lokales Intranet"), müssen Sie entscheiden, wie sich Ihre Anwendung in dieser Umgebung verhalten soll. Windows Forms bietet andere, sicherere Möglichkeiten zum Implementieren von Features, wenn die Zielumgebung eine teilweise vertrauenswürdige Umgebung ist. Bestimmte Teile Ihrer Anwendung, etwa Datenzugriff, können für teilweise und für voll vertrauenswürdige Umgebungen unterschiedlich entwickelt und geschrieben werden. Einige Windows Forms-Funktionen, etwa Anwendungseinstellungen, sind dafür entworfen, mit teilweiser Vertrauenswürdigkeit verwendet zu werden. Weitere Informationen finden Sie unter [Übersicht über Anwendungseinstellungen](../../../docs/framework/winforms/advanced/application-settings-overview.md).  
  
 Wenn Ihre Anwendung mehr Berechtigungen erfordert, als teilweise Vertrauenswürdigkeit zulässt, Sie die Anwendung aber nicht mit voller Vertrauenswürdigkeit ausführen möchten, können Sie sie mit teilweiser Vertrauenswürdigkeit ausführen und ihr nur die zusätzlich erforderlichen Berechtigungen gewähren. Möchten Sie Ihre Anwendung beispielsweise mit teilweiser Vertrauenswürdigkeit ausführen, müssen Sie ihr aber Lesezugriff auf ein Verzeichnis im Dateisystem des Benutzers gewähren, können Sie <xref:System.Security.Permissions.FileIOPermission> nur für dieses Verzeichnis anfordern. Wenn Sie diesen Ansatz konsequent umsetzen, können Sie für Ihre Anwendung erhöhte Funktionalität erreichen und die Sicherheitsrisiken für die Benutzer minimieren.  
  
 Beim Entwickeln einer Anwendung, die mit teilweiser Vertrauenswürdigkeit ausgeführt wird, sollten Sie verfolgen, mit welchen Berechtigungen die Anwendung ausgeführt werden muss und welche Berechtigungen sie möglicherweise optional verwendet. Wenn Ihnen alle erforderlichen Berechtigungen bekannt sind, sollten Sie auf Anwendungsebene eine deklarative Anforderung für Berechtigungen ausführen. Durch Anfordern von Berechtigungen wird [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Run Time mitgeteilt, welche Berechtigungen Ihre Anwendung benötigt und welche sie speziell nicht wünscht. Weitere Informationen zum Anfordern von Berechtigungen finden Sie unter [Anfordern von Berechtigungen](https://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2).  
  
 Wenn Sie optionale Berechtigungen anfordern, müssen Sie Sicherheitsausnahmen behandeln, die generiert werden, wenn Ihre Anwendung eine Aktion durchführt, die Berechtigungen erfordert, die ihr nicht erteilt wurden. Durch ordnungsgemäße Behandlung der <xref:System.Security.SecurityException>-Instanz wird sichergestellt, dass Ihre Anwendung weiter ausgeführt werden kann. Ihre Anwendung kann die Ausnahme verwenden, um zu bestimmen, ob eine Funktion für den Benutzer deaktiviert werden sollte. Beispielsweise kann eine Anwendung die Menüoption **Speichern** deaktivieren, wenn die erforderliche Dateiberechtigung nicht gewährt wurde.  
  
 Manchmal ist es schwierig zu wissen, ob Sie alle entsprechenden Berechtigungen bedacht haben. Ein Methodenaufruf, der in der Oberfläche harmlos aussieht, kann z. B. irgendwann während seiner Ausführung auf das Dateisystem zugreifen. Wenn Sie Ihre Anwendung nicht mit allen erforderlichen Berechtigungen bereitstellen, kann es passieren, dass sie in Tests beim Debuggen auf Ihrem Desktop einwandfrei ausgeführt wird, aber fehlschlägt, wenn sie bereitgestellt ist. Sowohl die [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] SDK und Visual Studio 2005 enthalten Tools für die Berechtigungen eine Anwendung benötigt: der MT.exe Befehl Tools "Linie" und das Feature "Berechtigungen berechnen" von Visual Studio.  
  
 In den folgenden Themen sind zusätzliche Sicherheitsfeatures von Windows Forms beschrieben.  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|-   [Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)|Beschreibt, wie in einer teilweise vertrauenswürdigen Umgebung auf Dateien und Daten zugegriffen wird.|  
|-   [Mehr Sicherheit beim Drucken in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)|Beschreibt, wie in einer teilweise vertrauenswürdigen Umgebung auf Druckfunktionen zugegriffen wird.|  
|-   [Weitere Überlegungen zur Sicherheit in Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)|Beschreibt das Bearbeiten von Fenstern, Verwenden der Zwischenablage und das Aufrufen von nicht verwaltetem Code in einer teilweise vertrauenswürdigen Umgebung.|  
  
-  
  
### <a name="deploying-an-application-with-the-appropriate-permissions"></a>Bereitstellen einer Anwendung mit den entsprechenden Berechtigungen  
 Die häufigste Methode der Bereitstellung einer Windows Forms-Anwendung für einen Clientcomputer ist [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)], eine Bereitstellungstechnologie, mit der alle Komponenten beschrieben werden, die Ihre Anwendung zur Ausführung benötigt. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] verwendet XML-Dateien, die als Manifeste bezeichnet werden. In diesen XML-Dateien sind die Assemblys und Dateien, aus denen Ihre Anwendung besteht, sowie die Berechtigungen beschrieben, die für die Anwendung erforderlich sind.  
  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] verwendet zwei Technologien zum Anfordern von erweiterten Berechtigungen auf einem Clientcomputer. Beide Technologien basieren auf der Verwendung von Authenticode-Zertifikaten. Die Zertifikate können den Benutzern ein gewisses Maß an Sicherheit geben, dass die Anwendung von einer vertrauenswürdigen Quelle stammt.  
  
 In der folgenden Liste sind diese Technologien beschrieben.  
  
|Technologie für erweiterte Berechtigungen|Beschreibung|  
|------------------------------------|-----------------|  
|Berechtigungserweiterung|Zeigt dem Benutzer ein Sicherheitsdialogfeld an, wenn er die Anwendung das erste Mal ausführt. Im Dialogfeld **Berechtigungserweiterung** wird der Benutzer darüber informiert, wer die Anwendung veröffentlicht hat. Der Benutzer kann dann anhand dieser Informationen entscheiden, ob er der Anwendung zusätzliche Vertrauenswürdigkeit gewährt.|  
|Bereitstellung einer vertrauenswürdigen Anwendung|Bedingt, dass ein Systemadministrator eine einmalige Installation des Authenticode-Zertifikats eines Herausgebers auf einem Clientcomputer ausführt. Ab diesem Zeitpunkt werden alle Anwendungen, die mit dem Zertifikat signiert sind, als vertrauenswürdig eingestuft, und sie können ohne zusätzliche Eingabeaufforderungen mit voller Vertrauenswürdigkeit auf dem lokalen Computer ausgeführt werden.|  
  
 Welche Technologie Sie wählen, hängt von Ihrer Bereitstellungsumgebung ab. Weitere Informationen finden Sie unter [Auswählen einer Strategie für die ClickOnce-Bereitstellung](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy).  
  
 In der Standardeinstellung [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] Anwendungen, die mit Visual Studio bereitgestellt oder die [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] SDK-Tools (Mage.exe und MageUI.exe) sind so konfiguriert, dass auf einem Clientcomputer ausführen, die über volle Vertrauenswürdigkeit verfügt. Wenn Sie Ihre Anwendung so bereitstellen, dass sie teilweise Vertrauenswürdigkeit oder nur einige zusätzlichen Berechtigungen hat, müssen Sie diese Standardeinstellung ändern. Hierzu können Sie mit Visual Studio oder der [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] SDK-Tool MageUI.exe, wenn Sie die Bereitstellung konfigurieren. Weitere Informationen zur Verwendung von "MageUI.exe" finden Sie unter "Exemplarische Vorgehensweise: Bereitstellen einer ClickOnce-Anwendung von der Befehlszeile aus".  Siehe auch [Vorgehensweise: Festlegen benutzerdefinierter Berechtigungen für eine ClickOnce-Anwendung](https://msdn.microsoft.com/library/hafybdaa\(v=vs.110\)) oder [Vorgehensweise: Festlegen benutzerdefinierter Berechtigungen für eine ClickOnce-Anwendung](https://msdn.microsoft.com/library/hafybdaa\(v=vs.120\)).  
  
 Weitere Informationen zu den Sicherheitsaspekten von [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] und der Berechtigungserweiterung finden Sie unter [ClickOnce-Bereitstellung und -Sicherheit](/visualstudio/deployment/securing-clickonce-applications). Weitere Informationen zur Bereitstellung vertrauenswürdiger Anwendungen finden Sie unter [Übersicht über die Bereitstellung vertrauenswürdiger Anwendungen](/visualstudio/deployment/trusted-application-deployment-overview).  
  
### <a name="testing-the-application"></a>Testen der Anwendung  
 Wenn Sie Ihre Windows Forms-Anwendung mit Visual Studio bereitgestellt haben, können Sie das Debuggen in teilweiser Vertrauenswürdigkeit oder in einem eingeschränkten Berechtigungssatz aus der Entwicklungsumgebung aktivieren.  Siehe auch [Vorgehensweise: Debuggen einer ClickOnce-Anwendung mit eingeschränkten Berechtigungen](https://msdn.microsoft.com/library/593zkfdf\(v=vs.110\)) oder [Vorgehensweise: Debuggen einer ClickOnce-Anwendung mit eingeschränkten Berechtigungen](https://msdn.microsoft.com/library/593zkfdf\(v=vs.120\)).  
  
## <a name="see-also"></a>Siehe auch  
 [Sicherheit in Windows Forms](../../../docs/framework/winforms/windows-forms-security.md)  
 [Grundlagen der Codezugriffssicherheit](../../../docs/framework/misc/code-access-security-basics.md)  
 [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)  
 [Überblick über die Bereitstellung vertrauenswürdiger Anwendungen](/visualstudio/deployment/trusted-application-deployment-overview)  
 [Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)  
 [MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
