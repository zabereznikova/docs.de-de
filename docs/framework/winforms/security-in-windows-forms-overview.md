---
title: Sicherheitsübersicht
ms.date: 03/30/2017
helpviewer_keywords:
- code access security [Windows Forms], Windows Forms
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms], about security
- access control [Windows Forms], Windows Forms
ms.assetid: 4810dc9f-ea23-4ce1-8ea1-657f0ff1d820
ms.openlocfilehash: 9010b45383f856079661359fdf82180526d96dde
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734842"
---
# <a name="security-in-windows-forms-overview"></a>Übersicht über die Sicherheit in Windows Forms

Vor der Veröffentlichung des .NET Framework besaß der gesamte Code, der auf dem Computer eines Benutzers ausgeführt wird, die gleichen Rechte oder Berechtigungen für den Zugriff auf Ressourcen, die ein Benutzer des Computers besaß. Wenn der Benutzer beispielsweise berechtigt war, auf das Dateisystem zuzugreifen, war auch der Code berechtigt, auf das Dateisystem zuzugreifen. Wenn der Benutzer Zugriffsrechte für eine Datenbank hatte, konnte der Code ebenfalls auf diese Datenbank zugreifen. Diese Berechtigungen können für Code in ausführbaren Dateien akzeptabel sein, die der Benutzer explizit auf dem lokalen Computer installiert hat. Sie sind aber wahrscheinlich nicht für potenzielle Schadsoftware akzeptabel, der aus dem Internet oder einem lokalen Intranet stammt. Dieser Code darf nicht ohne Berechtigung auf Computerressourcen des Benutzers zugreifen können.

In der .NET Framework wird eine Infrastruktur mit dem Namen "Code Zugriffssicherheit" eingeführt, mit der Sie die Berechtigungen oder Rechte, die der Code hat, über die Rechte des Benutzers unterscheiden können. Standardmäßig kann Code, der aus dem Internet oder dem Intranet stammt, nur in der Umgebung ausgeführt werden, die als teilweise vertrauenswürdige Umgebung bezeichnet wird. Teilweise Vertrauenswürdigkeit bedingt für eine Anwendung eine Reihe von Beschränkungen: Neben anderen Aspekten kann eine Anwendung weder auf die lokale Festplatte zugreifen noch nicht verwalteten Code ausführen. Der .NET Framework steuert die Ressourcen, auf die der Code basierend auf der Identität des Codes zugreifen kann: woher er stammt, ob er Assemblys mit [starkem Namen](../../standard/assembly/strong-named.md)hat, ob er mit einem Zertifikat signiert ist usw.

Die ClickOnce-Technologie, mit der Sie Windows Forms-Anwendungen bereitstellen, erleichtert Ihnen das Entwickeln von Anwendungen, die mit teilweiser Vertrauenswürdigkeit, voller Vertrauenswürdigkeit oder teilweiser Vertrauenswürdigkeit mit erweiterten Berechtigungen ausgeführt werden. ClickOnce bietet Features wie Berechtigungs Erweiterung und Bereitstellung vertrauenswürdiger Anwendungen, sodass Ihre Anwendung volle Vertrauenswürdigkeit oder erweiterte Berechtigungen vom lokalen Benutzer anfordern kann.

## <a name="understanding-security-in-the-net-framework"></a>Grundlegendes zur Sicherheit in .NET Framework

Mithilfe der Codezugriffssicherheit können für Code anhand seines Ursprungs und weiterer Aspekte seiner Identität verschiedene Vertrauensebenen festgelegt werden. Weitere Informationen zu den Beweisen, die Common Language Runtime zum Ermitteln der Sicherheitsrichtlinien verwendet, finden Sie unter [Beweis](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd(v=vs.100)). Sie unterstützt dabei, Computersysteme vor Schadsoftware zu schützen, und sie schützt vertrauenswürdigen Code davor, absichtlich oder versehentlich die Sicherheit zu gefährden. Codezugriffssicherheit gibt Ihnen außerdem mehr Kontrolle über die Aktionen, die Ihre Anwendung ausführen kann, weil Sie die Möglichkeit haben, nur die Berechtigungen anzugeben, die für die Anwendung benötigt werden. Codezugriffssicherheit betrifft den gesamten verwalteten Code, der auf der Common Language Runtime aufsetzt, selbst wenn dieser Code keine einzige Berechtigungsüberprüfung für Codezugriffssicherheit ausführt. Weitere Informationen zur Sicherheit in der .NET Framework finden Sie unter [wichtige Sicherheitskonzepte](../../standard/security/key-security-concepts.md) und [Grundlagen der Code Zugriffssicherheit](../misc/code-access-security-basics.md).

Wenn der Benutzer eine ausführbare Windows Forms-Datei direkt aus einem Webserver oder über eine Dateifreigabe ausführt, hängt der Grad der Vertrauenswürdigkeit, die Ihrer Anwendung gewährt wird, davon ab, wo sich der Code befindet und wie er gestartet wurde. Wenn eine Anwendung ausgeführt wird, wird sie automatisch ausgewertet, und erhält sie einen benannten Berechtigungssatz von der Common Language Runtime. Standardmäßig wird Code vom lokalen Computer der Berechtigungssatz "Voll vertrauenswürdig", Code aus einem lokalen Netzwerk der Berechtigungssatz "Lokales Intranet" und Code aus dem Internet der Berechtigungssatz "Internet" gewährt.

> [!NOTE]
> In den .NET Framework, Version 1,0, Service Pack 1 und Service Pack 2, erhält die Internet Zonen-Codegruppe den Berechtigungs Satz "Nothing". In allen anderen Versionen des .NET Framework empfängt die Internet Zonen-Codegruppe die festgelegten Internet Berechtigungen.
>
> Die Standardberechtigungen, die in jedem dieser Berechtigungssätze gewährt werden, werden im Thema [Standardmäßige Sicherheitsrichtlinie](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100)) aufgeführt. Abhängig von den Berechtigungen, die eine Anwendung erhält, wird sie ordnungsgemäß ausgeführt oder wird eine Sicherheitsausnahme ausgelöst.
>
> Viele Windows Forms Anwendungen werden mithilfe von ClickOnce bereitgestellt. Die Tools, die zum Erstellen einer ClickOnce-Bereitstellung verwendet werden, haben unterschiedliche Sicherheits Standardwerte als zuvor erläutert wurden. Weitere Informationen finden Sie im folgenden Abschnitt.

Die tatsächlichen Berechtigungen, die Ihrer Anwendung gewährt werden, können sich von den Standardwerten unterscheiden, weil die Sicherheitsrichtlinie geändert werden kann. Dies kann dazu führen, dass Ihre Anwendung auf einem Computer Berechtigung hat, auf einem anderen jedoch nicht.

## <a name="developing-a-more-secure-windows-forms-application"></a>Entwickeln einer sichereren Windows Forms-Anwendung

Sicherheit ist bei allen Schritten der Entwicklung von Anwendungen wichtig. Beginnen Sie, indem Sie die [Richtlinien für das Schreiben von sicherem Code](../../standard/security/secure-coding-guidelines.md) lesen.

Legen Sie dann fest, ob Ihre Anwendung mit voller Vertrauenswürdigkeit ausgeführt werden muss oder ob sie mit teilweiser Vertrauenswürdigkeit ausgeführt werden soll. Ein Ausführen Ihrer Anwendung mit voller Vertrauenswürdigkeit erleichtert den Zugriff auf Ressourcen auf dem lokalen Computer, setzt Ihre Anwendung und deren Benutzer aber hohen Sicherheitsrisiken aus, sofern Sie die Anwendung nicht genau entsprechend dem Thema "Richtlinien für das Schreiben von sicherem Code" entworfen und entwickelt haben. Ein Ausführen Ihrer Anwendung mit teilweiser Vertrauenswürdigkeit erleichtert es, eine sicherere Anwendung zu entwickeln, und verringert großenteils das Risiko, erfordert jedoch mehr Planung, wie bestimmte Features zu implementieren sind.

Wenn Sie teilweise Vertrauenswürdigkeit wählen (also entweder den Berechtigungssatz "Internet" oder "Lokales Intranet"), müssen Sie entscheiden, wie sich Ihre Anwendung in dieser Umgebung verhalten soll. Windows Forms bietet andere, sicherere Möglichkeiten zum Implementieren von Features, wenn die Zielumgebung eine teilweise vertrauenswürdige Umgebung ist. Bestimmte Teile Ihrer Anwendung, etwa Datenzugriff, können für teilweise und für voll vertrauenswürdige Umgebungen unterschiedlich entwickelt und geschrieben werden. Einige Windows Forms-Funktionen, etwa Anwendungseinstellungen, sind dafür entworfen, mit teilweiser Vertrauenswürdigkeit verwendet zu werden. Weitere Informationen finden Sie unter [Übersicht über Anwendungseinstellungen](./advanced/application-settings-overview.md).

Wenn Ihre Anwendung mehr Berechtigungen erfordert, als teilweise Vertrauenswürdigkeit zulässt, Sie die Anwendung aber nicht mit voller Vertrauenswürdigkeit ausführen möchten, können Sie sie mit teilweiser Vertrauenswürdigkeit ausführen und ihr nur die zusätzlich erforderlichen Berechtigungen gewähren. Möchten Sie Ihre Anwendung beispielsweise mit teilweiser Vertrauenswürdigkeit ausführen, müssen Sie ihr aber Lesezugriff auf ein Verzeichnis im Dateisystem des Benutzers gewähren, können Sie <xref:System.Security.Permissions.FileIOPermission> nur für dieses Verzeichnis anfordern. Wenn Sie diesen Ansatz konsequent umsetzen, können Sie für Ihre Anwendung erhöhte Funktionalität erreichen und die Sicherheitsrisiken für die Benutzer minimieren.

Beim Entwickeln einer Anwendung, die mit teilweiser Vertrauenswürdigkeit ausgeführt wird, sollten Sie verfolgen, mit welchen Berechtigungen die Anwendung ausgeführt werden muss und welche Berechtigungen sie möglicherweise optional verwendet. Wenn Ihnen alle erforderlichen Berechtigungen bekannt sind, sollten Sie auf Anwendungsebene eine deklarative Anforderung für Berechtigungen ausführen. Durch das Anfordern von Berechtigungen wird der .NET Framework Laufzeit mitgeteilt, welche Berechtigungen Ihre Anwendung benötigt und welche Berechtigungen Sie speziell nicht wünscht. Weitere Informationen zum Anfordern von Berechtigungen finden Sie unter [Anfordern von Berechtigungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100)).

Wenn Sie optionale Berechtigungen anfordern, müssen Sie Sicherheitsausnahmen behandeln, die generiert werden, wenn Ihre Anwendung eine Aktion durchführt, die Berechtigungen erfordert, die ihr nicht erteilt wurden. Durch ordnungsgemäße Behandlung der <xref:System.Security.SecurityException>-Instanz wird sichergestellt, dass Ihre Anwendung weiter ausgeführt werden kann. Ihre Anwendung kann die Ausnahme verwenden, um zu bestimmen, ob eine Funktion für den Benutzer deaktiviert werden sollte. Beispielsweise kann eine Anwendung die Menüoption **Speichern** deaktivieren, wenn die erforderliche Dateiberechtigung nicht gewährt wurde.

Manchmal ist es schwierig zu wissen, ob Sie alle entsprechenden Berechtigungen bedacht haben. Ein Methodenaufruf, der in der Oberfläche harmlos aussieht, kann z. B. irgendwann während seiner Ausführung auf das Dateisystem zugreifen. Wenn Sie Ihre Anwendung nicht mit allen erforderlichen Berechtigungen bereitstellen, kann es passieren, dass sie in Tests beim Debuggen auf Ihrem Desktop einwandfrei ausgeführt wird, aber fehlschlägt, wenn sie bereitgestellt ist. Sowohl das .NET Framework 2,0 SDK als auch Visual Studio 2005 enthalten Tools zum Berechnen der Berechtigungen, die eine Anwendung benötigt: das Befehlszeilen Tool "MT. exe" und das Feature "Berechtigungen berechnen" von Visual Studio.

In den folgenden Themen sind zusätzliche Sicherheitsfeatures von Windows Forms beschrieben.

|Thema|BESCHREIBUNG|
|-----------|-----------------|
|- [Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms](more-secure-file-and-data-access-in-windows-forms.md)|Beschreibt, wie in einer teilweise vertrauenswürdigen Umgebung auf Dateien und Daten zugegriffen wird.|
|- [Mehr Sicherheit beim Drucken in Windows Forms](more-secure-printing-in-windows-forms.md)|Beschreibt, wie in einer teilweise vertrauenswürdigen Umgebung auf Druckfunktionen zugegriffen wird.|
|- [Weitere Überlegungen zur Sicherheit in Windows Forms](additional-security-considerations-in-windows-forms.md)|Beschreibt das Bearbeiten von Fenstern, Verwenden der Zwischenablage und das Aufrufen von nicht verwaltetem Code in einer teilweise vertrauenswürdigen Umgebung.|

### <a name="deploying-an-application-with-the-appropriate-permissions"></a>Bereitstellen einer Anwendung mit den entsprechenden Berechtigungen

Die gängigste Methode, eine Windows Forms Anwendung auf einem Client Computer bereitzustellen, ist ClickOnce, eine Bereitstellungs Technologie, die alle Komponenten beschreibt, die Ihre Anwendung ausführen muss. ClickOnce verwendet XML-Dateien namens Manifeste, um die Assemblys und Dateien zu beschreiben, aus denen Ihre Anwendung besteht, sowie die Berechtigungen, die die Anwendung benötigt.

ClickOnce verfügt über zwei Technologien zum Anfordern von erweiterten Berechtigungen auf einem Client Computer. Beide Technologien basieren auf der Verwendung von Authenticode-Zertifikaten. Die Zertifikate können den Benutzern ein gewisses Maß an Sicherheit geben, dass die Anwendung von einer vertrauenswürdigen Quelle stammt.

In der folgenden Liste sind diese Technologien beschrieben.

|Technologie für erweiterte Berechtigungen|BESCHREIBUNG|
|------------------------------------|-----------------|
|Berechtigungserweiterung|Zeigt dem Benutzer ein Sicherheitsdialogfeld an, wenn er die Anwendung das erste Mal ausführt. Im Dialogfeld **Berechtigungserweiterung** wird der Benutzer darüber informiert, wer die Anwendung veröffentlicht hat. Der Benutzer kann dann anhand dieser Informationen entscheiden, ob er der Anwendung zusätzliche Vertrauenswürdigkeit gewährt.|
|Bereitstellung einer vertrauenswürdigen Anwendung|Bedingt, dass ein Systemadministrator eine einmalige Installation des Authenticode-Zertifikats eines Herausgebers auf einem Clientcomputer ausführt. Ab diesem Zeitpunkt werden alle Anwendungen, die mit dem Zertifikat signiert sind, als vertrauenswürdig eingestuft, und sie können ohne zusätzliche Eingabeaufforderungen mit voller Vertrauenswürdigkeit auf dem lokalen Computer ausgeführt werden.|

Welche Technologie Sie wählen, hängt von Ihrer Bereitstellungsumgebung ab. Weitere Informationen finden Sie unter [Auswählen einer Strategie für die ClickOnce-Bereitstellung](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy).

Standardmäßig sind ClickOnce-Anwendungen, die entweder mit Visual Studio oder den .NET Framework SDK-Tools (Mage. exe und MageUI. exe) bereitgestellt werden, für die Verwendung auf einem Client Computer mit voller Vertrauenswürdigkeit konfiguriert. Wenn Sie Ihre Anwendung so bereitstellen, dass sie teilweise Vertrauenswürdigkeit oder nur einige zusätzlichen Berechtigungen hat, müssen Sie diese Standardeinstellung ändern. Hierfür können Sie entweder Visual Studio oder das .NET Framework SDK-Tool "MageUI. exe" verwenden, wenn Sie die Bereitstellung konfigurieren. Weitere Informationen zur Verwendung von "MageUI. exe" finden Sie unter Exemplarische Vorgehensweise [: Manuelles Bereitstellen einer ClickOnce-Anwendung](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).  Siehe auch [Vorgehensweise: Festlegen benutzerdefinierter Berechtigungen für eine ClickOnce-Anwendung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/hafybdaa(v=vs.110)) oder [Vorgehensweise: Festlegen benutzerdefinierter Berechtigungen für eine ClickOnce-Anwendung](/visualstudio/deployment/how-to-set-custom-permissions-for-a-clickonce-application).

Weitere Informationen zu den Sicherheitsaspekten von ClickOnce und Berechtigungs Erweiterung finden Sie unter [Sichern von ClickOnce-Anwendungen](/visualstudio/deployment/securing-clickonce-applications). Weitere Informationen zur Bereitstellung vertrauenswürdiger Anwendungen finden Sie unter [Übersicht über die Bereitstellung vertrauenswürdiger Anwendungen](/visualstudio/deployment/trusted-application-deployment-overview).

### <a name="testing-the-application"></a>Testen der Anwendung

Wenn Sie die Windows Forms Anwendung mithilfe von Visual Studio bereitgestellt haben, können Sie das Debuggen in teilweiser Vertrauenswürdigkeit oder in einem eingeschränkten Berechtigungs Satz aus der Entwicklungsumgebung aktivieren.  Siehe auch Gewusst [wie: Debuggen einer ClickOnce-Anwendung mit eingeschränkten Berechtigungen](/visualstudio/deployment/how-to-debug-a-clickonce-application-with-restricted-permissions).

## <a name="see-also"></a>Weitere Informationen

- [Sicherheit in Windows Forms](windows-forms-security.md)
- [Grundlagen der Codezugriffssicherheit](../misc/code-access-security-basics.md)
- [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)
- [Überblick über die Bereitstellung vertrauenswürdiger Anwendungen](/visualstudio/deployment/trusted-application-deployment-overview)
- [Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)](../tools/mage-exe-manifest-generation-and-editing-tool.md)
- [MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
