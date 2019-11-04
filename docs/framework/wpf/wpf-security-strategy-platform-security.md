---
title: WPF-Sicherheitsstrategie – Plattformsicherheit
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform security model [WPF]
- Common Language Runtime (CLR) security features
- operating system security model [WPF]
- Internet Explorer security features [WPF]
- Security-Critical method
- CLR security features [WPF]
- security model [WPF]
- security model [WPF], platform
- WPF [WPF], about security model
- Windows Presentation Foundation [WPF], about security model
- security model [WPF], operating system
ms.assetid: 2a39a054-3e2a-4659-bcb7-8bcea490ba31
ms.openlocfilehash: 9c237c06de1388de4c1fe6a6edb3fb5b52522d1f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424628"
---
# <a name="wpf-security-strategy---platform-security"></a>WPF-Sicherheitsstrategie – Plattformsicherheit
Während Windows Presentation Foundation (WPF) eine Vielzahl von Sicherheitsdiensten bereitstellt, nutzt es auch die Sicherheitsfunktionen der zugrunde liegenden Plattform, die das Betriebssystem, die CLR und Internet Explorer umfasst. Im Zusammenspiel stellen diese Ebenen für [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] ein leistungsfähiges Modell für tiefgreifende, vorbeugende Sicherheitsmaßnahmen (Defense-in-Depth-Modell) bereit, das eine einzelne Fehlerquelle zu vermeiden sucht, wie aus der folgenden Abbildung hervorgeht:  
  
 ![Diagramm, das das WPF-Sicherheitsmodell zeigt.](./media/wpf-security-strategy-platform-security/windows-presentation-foundation-security.png)  
  
 Im weiteren Verlauf dieses Themas werden die Features auf den einzelnen Ebenen erläutert, die besonders [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] betreffen.  

## <a name="operating-system-security"></a>Betriebssystemsicherheit  
Der Kern von Windows bietet verschiedene Sicherheitsfeatures, die die Sicherheits Grundlage für alle Windows-Anwendungen bilden, einschließlich derjenigen, die mit WPF erstellt wurden. In diesem Thema wird der Umfang dieser Sicherheitsfeatures erläutert, die für WPF wichtig sind, sowie die Art und Weise, wie WPF in Sie integriert wird, um weitere Schutzmaßnahmen bereitzustellen.  
  
### <a name="microsoft-windows-xp-service-pack-2-sp2"></a>Microsoft Windows XP Service Pack 2 (SP2)  
 Zusätzlich zu einer allgemeinen Überprüfung und Verstärkung von Windows gibt es drei wichtige Features von [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)], die wir in diesem Thema erörtern werden:  
  
- /GS-Kompilierung  
  
- Microsoft-Windows Update.  
  
#### <a name="gs-compilation"></a>/GS-Kompilierung  
 [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] bietet Schutz durch das erneute Kompilieren vieler zentraler Systembibliotheken, einschließlich aller [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Abhängigkeiten (z. b. CLR), um Pufferüberläufe zu verringern. Dies wird mit dem /GS-Parameter und dem C/C++-Befehlszeilencompiler erreicht. Obwohl Pufferüberläufe ausdrücklich vermieden werden sollten, ist die Kompilierung mit /GS ein Beispiel für eine tiefgreifende Verteidigungsmaßnahme gegen potenzielle Sicherheitslücken, die versehentlich oder böswillig durch Pufferüberläufe erzeugt werden.  
  
 In der Vergangenheit waren Pufferüberläufe die Ursache für viele Sicherheitslücken mit gravierenden Folgen. Ein Pufferüberlauf tritt auf, wenn ein Angreifer die Sicherheitsanfälligkeit eines Codes nutzt, die das Einfügen von schädlichem Code ermöglicht, der über die Begrenzungen eines Puffers schreibt. Ein Angreifer kann dann durch Überschreiben der Rückgabeadresse einer Funktion den Prozess, in dem der Code ausgeführt wird, hacken und die Ausführung des Angreifercodes auslösen. Daraus entsteht bösartiger Code, der beliebigen Code mit den gleichen Berechtigungen wie der gehackte Prozess ausführt.  
  
 Auf hoher Ebene schützt das-GS-Compilerflag gegen einige potenzielle Pufferüberläufe, indem ein spezielles Sicherheits Cookie eingefügt wird, um die Rückgabeadresse einer Funktion zu schützen, die über lokale Zeichen folgen Puffer verfügt. Nach der Rückgabe einer Funktion wird das Sicherheitscookie mit seinem vorherigen Wert verglichen. Hat sich der Wert geändert, ist möglicherweise ein Pufferüberlauf aufgetreten, und der Prozess wird mit einer Fehlerbedingung beendet. Das Beenden des Prozesses verhindert die Ausführung von potenziell bösartigem Code. Weitere Informationen finden Sie unter [-GS (Puffer-Sicherheitsüberprüfung)](/cpp/build/reference/gs-buffer-security-check) .  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] wird mit dem /GS-Flag kompiliert, um eine weitere Schutzebene für [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen bereitzustellen.  
  
### <a name="windows-vista"></a>Windows Vista  
WPF-Benutzer unter Windows Vista profitieren von den zusätzlichen Sicherheitserweiterungen des Betriebssystems, einschließlich "Benutzer Zugriff mit geringsten Rechten", Code Integritätsprüfungen und Berechtigungs Isolation.  
  
#### <a name="user-account-control-uac"></a>Benutzerkontensteuerung (User Account Control, UAC)  
 Heutzutage werden Windows-Benutzer tendenziell mit Administratorrechten ausgeführt, da Sie von vielen Anwendungen sowohl für die Installation als auch für die Ausführung oder beides benötigt werden. Das Schreiben von Standardanwendungseinstellungen in die Registrierung ist nur ein Beispiel.  
  
 Das Arbeiten mit Administratorrechten bedeutet im Grunde, dass Anwendungen von Prozessen ausgeführt werden, denen Administratorrechte gewährt werden. Das hat Auswirkungen auf die Sicherheit, denn bösartiger Code, der zum Hacken eines mit Administratorrechten ausgeführten Prozesses verwendet wird, übernimmt automatisch dessen Berechtigungen, einschließlich des Zugriffs auf kritische Systemressourcen.  
  
 Anwendungen nur mit den unbedingt erforderlichen Berechtigungen auszuführen, ist eine Möglichkeit, sich vor dieser Sicherheitsbedrohung zu schützen. Dies wird als Prinzip der geringsten Rechte bezeichnet und ist ein zentrales Feature des Windows-Betriebssystems. Diese Funktion wird als Benutzerkontensteuerung (User Account Control, UAC) bezeichnet und wird von Windows UAC auf zwei Arten verwendet:  
  
- Die meisten Anwendungen werden standardmäßig mit den Rechten der Benutzerkontensteuerung ausgeführt, selbst wenn der Benutzer ein Administrator ist; nur Anwendungen, die Administratorrechte benötigen, werden mit Administratorrechten ausgeführt. Um mit Administratorrechten ausgeführt zu werden, müssen Anwendungen entweder in ihrem Anwendungsmanifest oder als Eintrag in der Sicherheitsrichtlinie besonders gekennzeichnet werden.  
  
- Bereitstellen von Kompatibilitätslösungen wie die Virtualisierung. Viele Anwendungen versuchen beipielsweise, in eingeschränkte Speicherorte wie "C:\Programme" zu schreiben. Für Anwendungen, die über die Benutzerkontensteuerung ausgeführt werden, steht ein alternativer benutzerbezogener Speicherort zur Verfügung, der für Schreibvorgänge keine Administratorrechte erfordert. Für Anwendungen, die über die Benutzerkontensteuerung ausgeführt werden, wird "C:\Programme" virtualisiert. Dadurch wird der Anschein erweckt, dass die Anwendungen in dieses Verzeichnis schreiben, obwohl sie stattdessen in den alternativen, benutzerbezogenen Speicherort schreiben. Dank dieser Art von Kompatibilität kann das Betriebssystem viele Anwendungen ausführen, die zuvor nicht mit der Benutzerkontensteuerung ausgeführt werden konnten.  
  
#### <a name="code-integrity-checks"></a>Integritätsprüfungen für Code  
 Windows Vista enthält tiefere Code Integritätsprüfungen, um zu verhindern, dass bösartiger Code zur Lade-/Laufzeit in Systemdateien oder in den Kernel eingefügt wird. Dies geht über den Schutz der Systemdateien hinaus.  
   
### <a name="limited-rights-process-for-browser-hosted-applications"></a>Prozess mit eingeschränkten Rechten für im Browser gehostete Anwendungen  
 Im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen werden im Sicherheitssandkasten der Internetzone ausgeführt. durch die [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Integration in Microsoft Internet Explorer wird dieser Schutz um zusätzliche Unterstützung erweitert.  
  
 Da XAML-Browser Anwendungen (XBAPs) in der Regel durch den Berechtigungs Satz für die Internet Zone in einem Sandkasten verwendet werden, werden XAML-Browser Anwendungen (XBAPs) durch das Entfernen dieser Berechtigungen aus Kompatibilitäts Sicht nicht beeinträchtigt. Stattdessen wird eine zusätzliche Defense-in-Depth-Ebene geschaffen. Wenn eine in einem Sicherheitssandkasten ausgeführte Anwendung in der Lage ist, andere Ebenen anzugreifen und den Prozess zu hacken, verfügt auch der Prozess nur über eingeschränkte Berechtigungen.  
  
 Weitere Informationen finden [Sie unter Verwenden eines Benutzerkontos mit den geringsten Rechten](https://docs.microsoft.com/previous-versions/tn-archive/cc700846%28v=technet.10%29).  
  
## <a name="common-language-runtime-security"></a>Common Language Runtime-Sicherheit  
 Der Common Language Runtime (CLR) bietet eine Reihe von wichtigen Sicherheitsvorteilen, einschließlich Validierung und Überprüfung, Code Zugriffssicherheit (Code Access Security, CAS) und der sicherheitskritischen Methodik.  
    
### <a name="validation-and-verification"></a>Validierung und Prüfung  
 Zum Bereitstellen von Assemblyisolation und-Integrität verwendet die CLR einen Validierungsprozess. Die CLR-Überprüfung stellt sicher, dass Assemblys isoliert werden, indem das PE-Dateiformat (portable ausführbare Datei) für Adressen, die auf die Assembly verweisen Die CLR-Überprüfung überprüft auch die Integrität der Metadaten, die in eine Assembly eingebettet sind.  
  
 Um die Typsicherheit zu gewährleisten, häufige Sicherheitsprobleme (z. b. Pufferüberläufe) zu vermeiden und Sandkasten durch die unter Prozess Isolation zu ermöglichen, verwendet die CLR-Sicherheit das Konzept der Überprüfung.  
  
 Verwaltete Anwendungen werden in Microsoft Intermediate Language (MSIL) kompiliert. Wenn Methoden in einer verwalteten Anwendung ausgeführt werden, wird die MSIL über Just-in-Time (JIT)-Kompilierung in systemeigenen Code kompiliert. Die JIT-Kompilierung enthält einen Prüfprozess mit vielen Sicherheits- und Stabilitätsregeln, die sicherstellen, dass der Code keine der folgenden Eigenschaften aufweist:  
  
- Verletzen von Typverträgen  
  
- Verursachen von Pufferüberläufen  
  
- Unkontrollierter Zugriff auf den Arbeitsspeicher  
  
 Verwalteter Code, der den Prüfregeln nicht entspricht, darf nur dann ausgeführt werden, wenn er als vertrauenswürdiger Code gilt.  
  
 Der Vorteil von überprüfbarem Code ist ein wichtiger Grund, warum [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] auf dem .NET Framework aufbaut. Mit zunehmender Verwendung prüfbaren Codes sinkt die Wahrscheinlichkeit, dass potenzielle Schwachstellen ausgenutzt werden, ganz erheblich.  
  
### <a name="code-access-security"></a>Codezugriffssicherheit  
 Ein Clientcomputer stellt eine Vielzahl von Ressourcen bereit, auf die eine verwaltete Anwendung zugreifen kann. Dazu zählen u. a. Dateisystem, Registrierung, Druckdienste, Benutzeroberfläche, Reflektion und Umgebungsvariablen. Bevor eine verwaltete Anwendung auf eine Ressource auf einem Client Computer zugreifen kann, muss Sie über .NET Framework Berechtigung verfügen. Eine Berechtigung in CAS ist eine Unterklasse des <xref:System.Security.CodeAccessPermission>; CAS implementiert eine Unterklasse für jede Ressource, auf die verwaltete Anwendungen zugreifen können.  
  
 Der Berechtigungs Satz, den eine verwaltete Anwendung von CAS bei der Ausführung erhält, wird als Berechtigungs Satz bezeichnet und wird durch von der Anwendung bereitgestellte Beweise bestimmt. Bei [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen wird als Nachweis der Speicherort oder die Zone bereitgestellt, von dem bzw. der die Anwendungen gestartet werden. CAS identifiziert die folgenden Zonen:  
  
- **Arbeitsplatz**. Anwendungen, die auf dem Clientcomputer gestartet werden (voll vertrauenswürdig).  
  
- **Lokales Intranet**. Anwendungen, die aus dem Intranet gestartet werden (in gewisser Weise vertrauenswürdig).  
  
- **Internet**. Anwendungen, die aus dem Internet gestartet werden (wenig vertrauenswürdig).  
  
- **Vertrauenswürdige Sites**. Anwendungen, die von einem Benutzer als vertrauenswürdig identifiziert wurden (wenig vertrauenswürdig).  
  
- **Nicht vertrauenswürdige Sites**. Anwendungen, die von einem Benutzer als nicht vertrauenswürdig identifiziert wurden (nicht vertrauenswürdig).  
  
 Für jede dieser Zonen stellt CAS einen vordefinierten Berechtigungs Satz bereit, der die Berechtigungen enthält, die der zugeordneten Vertrauens Ebene entsprechen. Dazu gehören:  
  
- **FullTrust**. Für Anwendungen, die aus der **Arbeitsplatz** Zone gestartet werden. Alle möglichen Berechtigungen werden gewährt.  
  
- **LocalIntranet**. Für Anwendungen, die aus der **lokalen Intranetzone** gestartet werden. Für einen moderaten Zugriff auf die Ressourcen des Clientcomputers wird eine Teilmenge von Berechtigungen gewährt. Dazu zählen isolierter Speicher, uneingeschränkter Zugriff auf die Benutzeroberfläche und Dateidialogfelder, eingeschränkte Reflektion sowie eingeschränkter Zugriff auf Umgebungsvariablen. Berechtigungen für kritische Ressourcen wie die Registrierung werden nicht bereitgestellt.  
  
- **Internet**. Für Anwendungen, die über die Zone **Internet** oder **Vertrauenswürdige Sites** gestartet werden. Für einen eingeschränkten Zugriff auf die Ressourcen des Clientcomputers wird eine Teilmenge von Berechtigungen gewährt. Dazu zählen isolierter Speicher, Öffnen von Dateien sowie eingeschränkter Zugriff auf die Benutzeroberfläche. Im wesentlichen isoliert dieser Berechtigungs Satz Anwendungen vom Client Computer.  
  
 Anwendungen, die als aus der Zone **nicht vertrauenswürdiger Sites** identifiziert werden, werden keinerlei Berechtigungen von CAS erteilt. Daher gibt es für diese Anwendungen keinen vordefinierten Berechtigungssatz.  
  
 In der folgenden Abbildung wird die Beziehung zwischen Zonen, Berechtigungs Sätzen, Berechtigungen und Ressourcen veranschaulicht:  
  
 ![Diagramm, in dem CAS-Berechtigungs Sätze angezeigt werden.](./media/wpf-security-strategy-platform-security/code-access-security-permissions-relationship.png)  
  
 Die Einschränkungen des Sicherheits Sandkastens der Internet Zone gelten in gleicher Weise für jeden Code, den eine XBAP aus einer Systembibliothek importiert, einschließlich [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]. Dadurch wird sichergestellt, dass jedes Bit des Codes (selbst [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]) gesperrt wird. Zum Ausführen von muss eine XBAP leider eine Funktionalität ausführen, die mehr Berechtigungen erfordert, als die von der Sicherheits Sandbox der Internet Zone aktivierten.  
  
 Stellen Sie sich eine XBAP-Anwendung vor, die die folgende Seite enthält:  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Um diese XBAP auszuführen, muss der zugrunde liegende [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Code mehr Funktionen ausführen, als für die Aufruf Bare XBAP verfügbar sind, einschließlich:  
  
- Erstellen eines Fenster Handles (HWND) für das Rendering  
  
- Verteilen von Nachrichten  
  
- Laden der Schriftart Tahoma  
  
 Unter dem Gesichtspunkt der Sicherheit wäre die Gewährung des direkten Zugriffs auf diese Vorgänge für die im Sicherheitssandkasten ausgeführte Anwendung eine Katastrophe.  
  
 Zum Glück bietet [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] einen Ausweg aus dieser Lage, indem es diesen Vorgängen die Ausführung mit erhöhten Rechten im Namen der im Sicherheitssandkasten ausgeführten Anwendung erlaubt. Während alle [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Vorgänge mit den eingeschränkten Sicherheits Berechtigungen der Internet Zone der Anwendungsdomäne der XBAP überprüft werden, wird [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] (wie bei anderen Systembibliotheken) ein Berechtigungs Satz gewährt, der alle möglichen Berechtigungen enthält.
  
 Dies setzt voraus, dass [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] erhöhte Rechte eingeräumt werden und gleichzeitig verhindert wird, dass diese Berechtigungen vom Berechtigungssatz der Internetzone der Hostanwendungsdomäne gesteuert werden.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] führt dies mithilfe der **Assert** -Methode einer Berechtigung aus. Der folgende Code beschreibt die Vorgehensweise.  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Durch die **Assert** -Berechtigung wird verhindert, dass die uneingeschränkten Berechtigungen, die von [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] erforderlich sind, durch die Berechtigungen der Internet Zone der XBAP eingeschränkt werden.  
  
 Aus Platt Form Sicht ist [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] für die korrekte Verwendung von **Assert** verantwortlich. eine falsche Verwendung von **Assert** könnte böswilligen Code ermöglichen, Berechtigungen zu erhöhen. Folglich ist es wichtig, dass Sie bei Bedarf nur **Assert** aufruft und sicherstellen, dass die Sandbox-Einschränkungen intakt bleiben. Beispielsweise darf im Sicherheitssandkasten ausgeführter Code zwar keine beliebigen Dateien öffnen, aber Schriftarten verwenden. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] ermöglicht es Sandkasten Anwendungen, die Schriftart Funktionalität durch Aufrufen von **Assert**zu verwenden, und für [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Dateien zu lesen, die bekanntermaßen diese Schriftarten im Namen der Sandbox-Anwendung enthalten.  
  
### <a name="clickonce-deployment"></a>ClickOnce-Bereitstellung  
 ClickOnce ist eine umfassende Bereitstellungs Technologie, die in .NET Framework enthalten ist und in Visual Studio integriert ist (Weitere Informationen finden Sie unter [ClickOnce-Sicherheit und-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment) ). Eigenständige [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Anwendungen können mithilfe von ClickOnce bereitgestellt werden, während im Browser gehostete Anwendungen mit ClickOnce bereitgestellt werden müssen.  
  
 Anwendungen, die mit ClickOnce bereitgestellt werden, erhalten über die Code Zugriffssicherheit (CAS) eine zusätzliche Sicherheitsschicht. im wesentlichen fordern ClickOnce-Anwendungen, die Sie benötigen, die erforderlichen Berechtigungen an. Diese Berechtigungen werden nur gewährt, wenn sie nicht höher sind als die Berechtigungen im Berechtigungssatz für die Zone, von der die Anwendung bereitgestellt wird. Durch die Reduzierung des Berechtigungs Satzes auf die benötigten Berechtigungen, selbst wenn Sie niedriger sind als die des Berechtigungs Satzes der Start Zone, wird die Anzahl der Ressourcen, auf die die Anwendung zugreifen kann, auf ein Minimum reduziert. Dadurch wird der mögliche Schaden für den Clientcomputer reduziert, falls die Anwendung gehackt wird.  
  
### <a name="security-critical-methodology"></a>Sicherheitsrelevante Methode  
 Der [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Code, der Berechtigungen verwendet, um den Internet Zonen-Sandkasten für XBAP-Anwendungen zu aktivieren, muss dem höchstmöglichen Maß an Sicherheitsüberwachung und-Kontrolle unterliegen. Um diese Anforderung zu vereinfachen, bietet .NET Framework eine neue Unterstützung für die Verwaltung von Code, der Berechtigungen erhöht. Die CLR ermöglicht es Ihnen, Code zu identifizieren, der Berechtigungen erhöht und ihn mit dem <xref:System.Security.SecurityCriticalAttribute> markiert. jeglicher Code, der nicht mit <xref:System.Security.SecurityCriticalAttribute> gekennzeichnet ist, wird mit dieser Methodik *transparent* . Umgekehrt wird verhindert, dass verwalteter Code, der nicht mit dem <xref:System.Security.SecurityCriticalAttribute> gekennzeichnet ist, die Rechte erhöht.  
  
 Die sicherheitsrelevante Methode ermöglicht die Organisation von [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Code, der Berechtigungen in den *sicherheitskritischen Kernel*erweitert, wobei der Rest transparent ist. Durch das Isolieren des sicherheitskritischen Codes kann sich das [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Engineering-Team auf eine zusätzliche Sicherheitsanalyse und Quell Code Verwaltung auf dem sicherheitskritischen Kernel konzentrieren, der oberhalb und über den standardmäßigen Sicherheitsverfahren liegt (siehe [WPF-Sicherheitsstrategie-Sicherheit). Engineering](wpf-security-strategy-security-engineering.md)).  
  
 Beachten Sie, dass .NET Framework vertrauenswürdigen Code ermöglicht, die XBAP-Internet Zonen Sandbox zu erweitern, indem Entwickler verwaltete Assemblys schreiben können, die mit <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) markiert sind und im globalen Assemblycache (GAC) des Benutzers bereitgestellt werden. Das Kennzeichnen einer Assembly mit dem APTCA-Attribut ist ein extrem kritischer Sicherheitsvorgang, da jeder Code, auch bösartiger Code aus dem Internet, diese Assembly aufrufen kann. Bei diesem Vorgang sind äußerste Vorsicht und die Verwendung bewährter Methoden ein absolutes Muss. Die Benutzer müssen zuerst angeben, dass sie dieser Software vertrauen, bevor sie installiert werden kann.  
  
## <a name="microsoft-internet-explorer-security"></a>Microsoft Internet Explorer-Sicherheit  
 Neben der Reduzierung von Sicherheitsproblemen und der Vereinfachung der Sicherheitskonfiguration enthält Microsoft Internet Explorer 6 (SP2) mehrere Features, die Sicherheitsverbesserungen für Benutzer von XAML-Browser Anwendungen (XBAPs) verbessern. Hauptziel dieser Features ist eine bessere Kontrolle des Benutzers über seine Arbeit im Brower.  
  
 Vor IE6 SP2 konnten Benutzer folgende Aktionen ausführen:  
  
- Zufällige Popupfenster  
  
- Verwirrende Skriptumleitung  
  
- Zahlreiche Sicherheitsdialogfelder auf manchen Websites  
  
 In einigen Fällen versuchen nicht vertrauenswürdige Websites, Benutzer durch Spoofing der Installation [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] oder wiederholt ein Microsoft ActiveX-Installations Dialogfeld anzuzeigen, auch wenn der Benutzer Sie möglicherweise abgebrochen hat. Mit diesen Techniken ist es möglich, eine große Anzahl von Benutzern zu schlechten Entscheidungen zu verleiten, die zur Installation von Spyware-Anwendungen führen.  
  
 IE6 SP2 umfasst mehrere Features, um diese Art von Problemen zu beheben, die sich auf das Konzept der Benutzer Initiierung beziehen. IE6 SP2 erkennt, wenn ein Benutzer vor einer Aktion auf einen Link oder ein Seitenelement geklickt hat, was als *Benutzer Initiierung*bezeichnet wird, und behandelt es anders, als wenn eine ähnliche Aktion stattdessen durch das Skript auf einer Seite ausgelöst wird. Beispielsweise enthält IE6 SP2 einen **Popup Blocker** , der erkennt, wenn ein Benutzer auf eine Schaltfläche klickt, bevor die Seite ein Popup erstellt. Dadurch kann IE6 SP2 die meisten unschädlichen Popups zulassen und gleichzeitig Popups verhindern, die Benutzer weder anfordern noch wünschen. Blockierte Popups werden unter der neuen **Informationsleiste**erfasst, sodass der Benutzer den Block manuell überschreiben und das Popup anzeigen kann.  
  
 Die gleiche Benutzer Initiierungs Logik wird auch zum Öffnen /**Speichern** von Sicherheits **Aufforderungen** angewendet. ActiveX-Installations Dialogfelder werden immer unter der Informationsleiste erfasst, es sei denn, Sie stellen ein Upgrade von einem zuvor installierten Steuerelement dar. All diese Maßnahmen sorgen für eine Benutzererfahrung mit mehr Sicherheit und Kontrolle und bieten Schutz vor Websites, die den Benutzer belästigen und zur Installation von unerwünschter oder schädlicher Software verleiten wollen.  
  
 Diese Features schützen außerdem Kunden, die IE6 SP2 zum Navigieren zu Websites verwenden, die es Ihnen ermöglichen, [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Anwendungen herunterzuladen und zu installieren. Dies ist insbesondere darauf zurückzuführen, dass IE6 SP2 eine bessere Benutzer Leistung bietet, die die Wahrscheinlichkeit verringert, dass Benutzer böswillige oder undurchsichtiger-Anwendungen installieren können, unabhängig davon, welche Technologie für die Erstellung verwendet wurde, einschließlich [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] wird diesen Schutzmaßnahmen mithilfe von ClickOnce hinzugefügt, um das Herunterladen von Anwendungen über das Internet zu vereinfachen. Da XAML-Browser Anwendungen (XBAPs) innerhalb eines Sicherheits Sandkastens der Internet Zone ausgeführt werden, können Sie nahtlos gestartet werden. Andererseits setzen eigenständige [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen volle Vertrauenswürdigkeit voraus, um ausgeführt werden zu können. Bei diesen Anwendungen zeigt ClickOnce während des Startvorgangs ein Sicherheits Dialogfeld an, um die Verwendung der zusätzlichen Sicherheitsanforderungen der Anwendung zu benachrichtigen. Da dies vom Benutzer initiiert werden muss, unterliegt der Vorgang außerdem der Benutzerinitiierungslogik und kann kann abgebrochen werden.  
  
 Internet Explorer 7 umfasst und erweitert die Sicherheitsfunktionen von IE6 SP2 im Rahmen eines kontinuierlichen Engagements der Sicherheit.  
  
## <a name="see-also"></a>Siehe auch

- [Codezugriffssicherheit](../misc/code-access-security.md)
- [Sicherheit](security-wpf.md)
- [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](wpf-partial-trust-security.md)
- [WPF-Sicherheitsstrategie – Sicherheitsentwicklung](wpf-security-strategy-security-engineering.md)
