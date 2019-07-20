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
ms.openlocfilehash: 0b39fce8bfd89dd11a863993738ef9b4fa64ba91
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364429"
---
# <a name="wpf-security-strategy---platform-security"></a>WPF-Sicherheitsstrategie – Plattformsicherheit
Während Windows Presentation Foundation (WPF) eine Vielzahl von Sicherheitsdiensten bereitstellt, nutzt es auch die Sicherheitsfunktionen der zugrunde liegenden Plattform, die das Betriebssystem, [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)]und [!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)]umfasst. Im Zusammenspiel stellen diese Ebenen für [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] ein leistungsfähiges Modell für tiefgreifende, vorbeugende Sicherheitsmaßnahmen (Defense-in-Depth-Modell) bereit, das eine einzelne Fehlerquelle zu vermeiden sucht, wie aus der folgenden Abbildung hervorgeht:  
  
 ![Diagramm, das das WPF-Sicherheitsmodell zeigt.](./media/wpf-security-strategy-platform-security/windows-presentation-foundation-security.png)  
  
 Im weiteren Verlauf dieses Themas werden die Features auf den einzelnen Ebenen erläutert, die besonders [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] betreffen.  

<a name="Operating_System_Security"></a>   
## <a name="operating-system-security"></a>Betriebssystemsicherheit  
 Für [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] ist als Betriebssystem mindestens [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] erforderlich. Der Kern von [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] bietet verschiedene Sicherheitsfeatures, die die Sicherheits Grundlage für alle Windows-Anwendungen bilden, einschließlich derjenigen [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], die mit erstellt wurden. [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)] enthält die Sicherheitsfeatures von [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] in erweiterter Form. In diesem Thema wird der Umfang dieser Sicherheitsfeatures behandelt, die für [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] wichtig sind. Erläutert wird auch die Integration mit [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], um weitere tiefgreifende Vorbeugungsmaßnahmen bereitzustellen.  
  
<a name="Microsoft_Windows_XP_Service_Pack_2__SP2_"></a>   
### <a name="microsoft-windows-xp-service-pack-2-sp2"></a>Microsoft Windows XP Service Pack 2 (SP2)  
 Zusätzlich zu einer allgemeinen Überprüfung und Verstärkung von Windows gibt es drei wichtige Features [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] , die in diesem Thema erläutert werden:  
  
- /GS-Kompilierung  
  
- [!INCLUDE[TLA#tla_win_update](../../../includes/tlasharptla-win-update-md.md)]  
  
#### <a name="gs-compilation"></a>/GS-Kompilierung  
 [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] bietet Schutz durch das erneute Kompilieren vieler zentraler Systembibliotheken, einschließlich aller [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Abhängigkeiten wie die [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)], um das Risiko von Pufferüberläufen zu verringern. Dies wird mit dem /GS-Parameter und dem C/C++-Befehlszeilencompiler erreicht. Obwohl Pufferüberläufe ausdrücklich vermieden werden sollten, ist die Kompilierung mit /GS ein Beispiel für eine tiefgreifende Verteidigungsmaßnahme gegen potenzielle Sicherheitslücken, die versehentlich oder böswillig durch Pufferüberläufe erzeugt werden.  
  
 In der Vergangenheit waren Pufferüberläufe die Ursache für viele Sicherheitslücken mit gravierenden Folgen. Ein Pufferüberlauf tritt auf, wenn ein Angreifer die Sicherheitsanfälligkeit eines Codes nutzt, die das Einfügen von schädlichem Code ermöglicht, der über die Begrenzungen eines Puffers schreibt. Ein Angreifer kann dann durch Überschreiben der Rückgabeadresse einer Funktion den Prozess, in dem der Code ausgeführt wird, hacken und die Ausführung des Angreifercodes auslösen. Daraus entsteht bösartiger Code, der beliebigen Code mit den gleichen Berechtigungen wie der gehackte Prozess ausführt.  
  
 Auf hoher Ebene schützt das /GS-Compilerflag vor einigen möglichen Pufferüberläufen, indem es zum Schutz der Rückgabeadresse einer Funktion, die über lokale Zeichenfolgepuffer verfügt, ein spezielles Sicherheitscookie einschleust. Nach der Rückgabe einer Funktion wird das Sicherheitscookie mit seinem vorherigen Wert verglichen. Hat sich der Wert geändert, ist möglicherweise ein Pufferüberlauf aufgetreten, und der Prozess wird mit einer Fehlerbedingung beendet. Das Beenden des Prozesses verhindert die Ausführung von potenziell bösartigem Code. Weitere Informationen finden Sie unter [/GS (Puffer-Sicherheitsüberprüfung)](/cpp/build/reference/gs-buffer-security-check) .  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] wird mit dem /GS-Flag kompiliert, um eine weitere Schutzebene für [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen bereitzustellen.  
  
#### <a name="microsoft-windows-update-enhancements"></a>Verbesserungen von Microsoft Windows Update  
 Auch [!INCLUDE[TLA#tla_win_update](../../../includes/tlasharptla-win-update-md.md)] wurde in [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] verbessert, um den Prozess des Herunterladens und Installierens von Updates zu vereinfachen. Durch diese Änderungen wird die Sicherheit für [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Kunden erheblich erhöht, da sie dafür sorgen, dass die Systeme der Kunden (besonders in Hinblick auf die Sicherheitsupdates) auf dem neuesten Stand sind.  
  
<a name="Windows_Vista"></a>   
### <a name="windows-vista"></a>Windows Vista  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Benutzer mit [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)] profitieren von zusätzlichen Verbesserungen des Betriebssystems in puncto Sicherheit, z. B. Benutzerkontensteuerung, Integritätsprüfungen für Code und Rechteisolierung.  
  
#### <a name="user-account-control-uac"></a>Benutzerkontensteuerung (User Account Control, UAC)  
 Heutzutage werden Windows-Benutzer tendenziell mit Administratorrechten ausgeführt, da Sie von vielen Anwendungen sowohl für die Installation als auch für die Ausführung oder beides benötigt werden. Das Schreiben von Standardanwendungseinstellungen in die Registrierung ist nur ein Beispiel.  
  
 Das Arbeiten mit Administratorrechten bedeutet im Grunde, dass Anwendungen von Prozessen ausgeführt werden, denen Administratorrechte gewährt werden. Das hat Auswirkungen auf die Sicherheit, denn bösartiger Code, der zum Hacken eines mit Administratorrechten ausgeführten Prozesses verwendet wird, übernimmt automatisch dessen Berechtigungen, einschließlich des Zugriffs auf kritische Systemressourcen.  
  
 Anwendungen nur mit den unbedingt erforderlichen Berechtigungen auszuführen, ist eine Möglichkeit, sich vor dieser Sicherheitsbedrohung zu schützen. Dieses sogenannte "Prinzip der geringsten Rechte" ist ein zentrales Feature des Betriebssystems [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)]. Diese als Benutzerkontensteuerung bezeichnete Funktion wird von [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)] auf zweierlei Weise verwendet:  
  
- Die meisten Anwendungen werden standardmäßig mit den Rechten der Benutzerkontensteuerung ausgeführt, selbst wenn der Benutzer ein Administrator ist; nur Anwendungen, die Administratorrechte benötigen, werden mit Administratorrechten ausgeführt. Um mit Administratorrechten ausgeführt zu werden, müssen Anwendungen entweder in ihrem Anwendungsmanifest oder als Eintrag in der Sicherheitsrichtlinie besonders gekennzeichnet werden.  
  
- Bereitstellen von Kompatibilitätslösungen wie die Virtualisierung. Viele Anwendungen versuchen beipielsweise, in eingeschränkte Speicherorte wie "C:\Programme" zu schreiben. Für Anwendungen, die über die Benutzerkontensteuerung ausgeführt werden, steht ein alternativer benutzerbezogener Speicherort zur Verfügung, der für Schreibvorgänge keine Administratorrechte erfordert. Für Anwendungen, die über die Benutzerkontensteuerung ausgeführt werden, wird "C:\Programme" virtualisiert. Dadurch wird der Anschein erweckt, dass die Anwendungen in dieses Verzeichnis schreiben, obwohl sie stattdessen in den alternativen, benutzerbezogenen Speicherort schreiben. Dank dieser Art von Kompatibilität kann das Betriebssystem viele Anwendungen ausführen, die zuvor nicht mit der Benutzerkontensteuerung ausgeführt werden konnten.  
  
#### <a name="code-integrity-checks"></a>Integritätsprüfungen für Code  
 [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)] enthält strengere Integritätsprüfungen für Code, um zu verhindern, dass bösartiger Code zur Lade-/Laufzeit in Systemdateien oder den Kernel eingeschleust wird. Dies geht über den Schutz der Systemdateien hinaus.  
  
<a name="Limited_Rights_Process_for_Browser_Hosted_Applications"></a>   
### <a name="limited-rights-process-for-browser-hosted-applications"></a>Prozess mit eingeschränkten Rechten für im Browser gehostete Anwendungen  
 Im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen werden im Sicherheitssandkasten der Internetzone ausgeführt. Die Integration von [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] mit [!INCLUDE[TLA#tla_ie](../../../includes/tlasharptla-ie-md.md)] erweitert diesen Schutz und stellt zusätzliche Unterstützung bereit.  
  
#### <a name="internet-explorer-6-service-pack-2-and-internet-explorer-7-for-xp"></a>Internet Explorer 6 Service Pack 2 und Internet Explorer 7 für XP  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] nutzt die Sicherheit des Betriebssystems für weiteren Schutz, indem es die Prozessberechtigungen für [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../includes/tlasharptla-winfxwebappsharpplural-md.md)] begrenzt. Bevor eine im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendung gestartet wird, erstellt das Betriebssystem einen Hostprozess, der unnötige Berechtigungen aus dem Prozesstoken entfernt. Zu den Berechtigungen, die entfernt werden, gehören beispielsweise das Herunterfahren des Computers des Benutzers, das Laden von Treibern und der Lesezugriff auf alle Dateien auf dem Computer.  
  
#### <a name="internet-explorer-7-for-vista"></a>Internet Explorer 7 für Vista  
 In [!INCLUDE[TLA#tla_ie7](../../../includes/tlasharptla-ie7-md.md)] werden [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen im geschützten Modus ausgeführt. Besonders [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)] werden mit mittlerer Integrität ausgeführt.  
  
#### <a name="defense-in-depth-layer"></a>Defense-In-Depth-Ebene  
 Da [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../includes/tlasharptla-winfxwebappsharpplural-md.md)] durch den Berechtigungssatz der Internetzone generell in einem Sicherheitssandkasten ausgeführt werden, wirkt sich das Entfernen dieser Berechtigungen unter Kompatibilitätsgesichtspunkten auf [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../includes/tlasharptla-winfxwebappsharpplural-md.md)] nicht negativ aus. Stattdessen wird eine zusätzliche Defense-in-Depth-Ebene geschaffen. Wenn eine in einem Sicherheitssandkasten ausgeführte Anwendung in der Lage ist, andere Ebenen anzugreifen und den Prozess zu hacken, verfügt auch der Prozess nur über eingeschränkte Berechtigungen.  
  
 Weitere Informationen finden [Sie unter Verwenden eines Benutzerkontos mit den geringsten Rechten](https://docs.microsoft.com/previous-versions/tn-archive/cc700846%28v=technet.10%29).  
  
<a name="Common_Language_Runtime_Security"></a>   
## <a name="common-language-runtime-security"></a>Common Language Runtime-Sicherheit  
 [!INCLUDE[TLA#tla_clr](../../../includes/tlasharptla-clr-md.md)] Bietet eine Reihe von wichtigen Sicherheitsvorteilen, einschließlich Validierung und Überprüfung, Code Zugriffssicherheit (Code Access Security, CAS) und der sicherheitskritischen Methodik.  
  
<a name="Validation_and_Verification"></a>   
### <a name="validation-and-verification"></a>Validierung und Prüfung  
 Assemblyisolation und Integrität wird von der [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] über einen Validierungsprozess bereitgestellt. Mit der [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)]-Validierung wird sichergestellt, dass Assemblys isoliert werden. Dazu wird deren PE (Portable Executable)-Dateiformat für Adressen validiert, die auf eine Stelle außerhalb der Assembly verweisen. Anhand der [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)]-Validierung wird auch die Integrität der in einer Assembly eingebetteten Metadaten validiert.  
  
 Um die Typsicherheit zu gewährleisten, häufige Sicherheitsprobleme (z. b. Pufferüberläufe) zu vermeiden und Sandkasten durch die unter [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] Prozess Isolation zu ermöglichen, verwendet die Sicherheit das Konzept der Überprüfung.  
  
 Verwaltete Anwendungen werden in Microsoft Intermediate Language (MSIL) kompiliert. Wenn Methoden in einer verwalteten Anwendung ausgeführt werden, wird die MSIL über Just-in-Time (JIT)-Kompilierung in systemeigenen Code kompiliert. Die JIT-Kompilierung enthält einen Prüfprozess mit vielen Sicherheits- und Stabilitätsregeln, die sicherstellen, dass der Code keine der folgenden Eigenschaften aufweist:  
  
- Verletzen von Typverträgen  
  
- Verursachen von Pufferüberläufen  
  
- Unkontrollierter Zugriff auf den Arbeitsspeicher  
  
 Verwalteter Code, der den Prüfregeln nicht entspricht, darf nur dann ausgeführt werden, wenn er als vertrauenswürdiger Code gilt.  
  
 Der Vorteil von überprüfbarem Code ist ein wichtiger [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Grund, warum auf dem .NET Framework aufbaut. Mit zunehmender Verwendung prüfbaren Codes sinkt die Wahrscheinlichkeit, dass potenzielle Schwachstellen ausgenutzt werden, ganz erheblich.  
  
<a name="Code_Access_Security"></a>   
### <a name="code-access-security"></a>Codezugriffssicherheit  
 Ein Clientcomputer stellt eine Vielzahl von Ressourcen bereit, auf die eine verwaltete Anwendung zugreifen kann. Dazu zählen u. a. Dateisystem, Registrierung, Druckdienste, Benutzeroberfläche, Reflektion und Umgebungsvariablen. Bevor eine verwaltete Anwendung auf eine Ressource auf einem Client Computer zugreifen kann, muss Sie über .NET Framework Berechtigung verfügen. Eine Berechtigung in CAS ist eine Unterklasse von <xref:System.Security.CodeAccessPermission>. CAS implementiert eine Unterklasse für jede Ressource, auf die verwaltete Anwendungen zugreifen können.  
  
 Der Berechtigungs Satz, den eine verwaltete Anwendung von CAS bei der Ausführung erhält, wird als Berechtigungs Satz bezeichnet und wird durch von der Anwendung bereitgestellte Beweise bestimmt. Bei [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen wird als Nachweis der Speicherort oder die Zone bereitgestellt, von dem bzw. der die Anwendungen gestartet werden. CAS identifiziert die folgenden Zonen:  
  
- **Arbeitsplatz**. Anwendungen, die auf dem Clientcomputer gestartet werden (voll vertrauenswürdig).  
  
- **Lokales Intranet**. Anwendungen, die aus dem Intranet gestartet werden (in gewisser Weise vertrauenswürdig).  
  
- **Internet**. Anwendungen, die aus dem Internet gestartet werden (wenig vertrauenswürdig).  
  
- **Vertrauenswürdige Sites**. Anwendungen, die von einem Benutzer als vertrauenswürdig identifiziert wurden (wenig vertrauenswürdig).  
  
- **Nicht vertrauenswürdige Sites**. Anwendungen, die von einem Benutzer als nicht vertrauenswürdig identifiziert wurden (nicht vertrauenswürdig).  
  
 Für jede dieser Zonen stellt CAS einen vordefinierten Berechtigungs Satz bereit, der die Berechtigungen enthält, die der zugeordneten Vertrauens Ebene entsprechen. Dazu gehören:  
  
- **FullTrust**. Für Anwendungen, die aus der **Arbeitsplatz** Zone gestartet werden. Alle möglichen Berechtigungen werden gewährt.  
  
- **LocalIntranet**. Für Anwendungen, die aus der **lokalen** Intranetzone gestartet werden. Für einen moderaten Zugriff auf die Ressourcen des Clientcomputers wird eine Teilmenge von Berechtigungen gewährt. Dazu zählen isolierter Speicher, uneingeschränkter Zugriff auf die Benutzeroberfläche und Dateidialogfelder, eingeschränkte Reflektion sowie eingeschränkter Zugriff auf Umgebungsvariablen. Berechtigungen für kritische Ressourcen wie die Registrierung werden nicht bereitgestellt.  
  
- **Internet**. Für Anwendungen, die über die Zone **Internet** oder **Vertrauenswürdige Sites** gestartet werden. Für einen eingeschränkten Zugriff auf die Ressourcen des Clientcomputers wird eine Teilmenge von Berechtigungen gewährt. Dazu zählen isolierter Speicher, Öffnen von Dateien sowie eingeschränkter Zugriff auf die Benutzeroberfläche. Im wesentlichen isoliert dieser Berechtigungs Satz Anwendungen vom Client Computer.  
  
 Anwendungen, die als aus der Zone **nicht vertrauenswürdiger Sites** identifiziert werden, werden keinerlei Berechtigungen von CAS erteilt. Daher gibt es für diese Anwendungen keinen vordefinierten Berechtigungssatz.  
  
 In der folgenden Abbildung wird die Beziehung zwischen Zonen, Berechtigungs Sätzen, Berechtigungen und Ressourcen veranschaulicht:  
  
 ![Diagramm, in dem CAS-Berechtigungs Sätze angezeigt werden.](./media/wpf-security-strategy-platform-security/code-access-security-permissions-relationship.png)  
  
 Die Einschränkungen des Sicherheits Sandkastens der Internet Zone gelten gleichermaßen für jeden Code, den eine XBAP aus einer System [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]Bibliothek importiert (einschließlich). Dadurch wird sichergestellt, dass jedes Bit des Codes (selbst [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]) gesperrt wird. Zum Ausführen von muss eine XBAP leider eine Funktionalität ausführen, die mehr Berechtigungen erfordert, als die von der Sicherheits Sandbox der Internet Zone aktivierten.  
  
 Stellen Sie sich eine XBAP-Anwendung vor, die die folgende Seite enthält:  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Um diese XBAP auszuführen, muss der [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] zugrunde liegende Code mehr Funktionen ausführen, als für die Aufruf Bare XBAP verfügbar sind, einschließlich:  
  
- Erstellen eines Fenster Handles (HWND) für das Rendering  
  
- Verteilen von Nachrichten  
  
- Laden der Schriftart Tahoma  
  
 Unter dem Gesichtspunkt der Sicherheit wäre die Gewährung des direkten Zugriffs auf diese Vorgänge für die im Sicherheitssandkasten ausgeführte Anwendung eine Katastrophe.  
  
 Zum Glück bietet [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] einen Ausweg aus dieser Lage, indem es diesen Vorgängen die Ausführung mit erhöhten Rechten im Namen der im Sicherheitssandkasten ausgeführten Anwendung erlaubt. Während alle [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Vorgänge mit den eingeschränkten Sicherheits Berechtigungen der Internet Zone der Anwendungsdomäne der XBAP überprüft werden, [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] wird (wie bei anderen Systembibliotheken) ein Berechtigungs Satz gewährt, der alle möglichen Berechtigungen enthält.
  
 Dies setzt voraus, dass [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] erhöhte Rechte eingeräumt werden und gleichzeitig verhindert wird, dass diese Berechtigungen vom Berechtigungssatz der Internetzone der Hostanwendungsdomäne gesteuert werden.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]Dies erfolgt mithilfe der **Assert** -Methode einer Berechtigung. Der folgende Code beschreibt die Vorgehensweise.  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Die **Assert** -Berechtigung verhindert im Wesentlichen, dass [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] die uneingeschränkten Berechtigungen, die von erforderlich sind, durch die Berechtigungen der Internet Zone der XBAP eingeschränkt werden.  
  
 Aus Platt Form Sicht [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] ist für die korrekte Verwendung von **Assert** verantwortlich; eine falsche Verwendung von **Assert** könnte böswilligen Code ermöglichen, Berechtigungen zu erhöhen. Folglich ist es wichtig, dass Sie bei Bedarf nur **Assert** aufruft und sicherstellen, dass die Sandbox-Einschränkungen intakt bleiben. Beispielsweise darf im Sicherheitssandkasten ausgeführter Code zwar keine beliebigen Dateien öffnen, aber Schriftarten verwenden. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]ermöglicht es Sandkasten Anwendungen, die Schriftart Funktionalität durch Aufrufen von **Assert**zu verwenden [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] , und für, um Dateien zu lesen, die bekanntermaßen diese Schriftarten im Namen der Sandbox-Anwendung enthalten.  
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a>ClickOnce-Bereitstellung  
 [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)]ist eine umfassende Bereitstellungs Technologie, die in .NET Framework enthalten ist und in [!INCLUDE[TLA#tla_visualstu](../../../includes/tlasharptla-visualstu-md.md)] integriert ist (Weitere Informationen finden Sie unter [ClickOnce-Sicherheit und-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment) ). Eigenständige [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen können mit [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] bereitgestellt werden, während im Browser gehostete Anwendungen mit [!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)] bereitgestellt werden müssen.  
  
 Anwendungen, die [!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)] mit bereitgestellt werden, erhalten eine zusätzliche Sicherheitsschicht über Code Zugriffssicherheit (Code [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] Access Security, CAS). im wesentlichen fordern bereitgestellte Anwendungen die benötigten Berechtigungen an. Diese Berechtigungen werden nur gewährt, wenn sie nicht höher sind als die Berechtigungen im Berechtigungssatz für die Zone, von der die Anwendung bereitgestellt wird. Durch die Reduzierung des Berechtigungs Satzes auf die benötigten Berechtigungen, selbst wenn Sie niedriger sind als die des Berechtigungs Satzes der Start Zone, wird die Anzahl der Ressourcen, auf die die Anwendung zugreifen kann, auf ein Minimum reduziert. Dadurch wird der mögliche Schaden für den Clientcomputer reduziert, falls die Anwendung gehackt wird.  
  
<a name="Security_Critical_Methodology"></a>   
### <a name="security-critical-methodology"></a>Sicherheitsrelevante Methode  
 Der [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Code, der Berechtigungen verwendet, um den Internet Zonen-Sandkasten für XBAP-Anwendungen zu aktivieren, muss dem größtmöglichen Maß an Sicherheitsüberwachung und-Kontrolle unterliegen. Um diese Anforderung zu vereinfachen, bietet .NET Framework eine neue Unterstützung für die Verwaltung von Code, der Berechtigungen erhöht. Insbesondere ermöglicht es [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] Ihnen, Code zu identifizieren, der Berechtigungen erhöht und ihn mit dem <xref:System.Security.SecurityCriticalAttribute>kennzeichnet. jeglicher Code, der <xref:System.Security.SecurityCriticalAttribute> nicht mit markiert ist, wird mit dieser Methodik *transparent* . Umgekehrt wird verhindert, dass verwalteter Code, der nicht mit dem <xref:System.Security.SecurityCriticalAttribute> gekennzeichnet ist, die Rechte erhöht.  
  
 Die sicherheitsrelevante Methodik ermöglicht der Organisation von [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Code, der Berechtigungen in den *sicherheitskritischen Kernel*erweitert, wobei der Rest transparent ist. Durch das Isolieren des sicherheitskritischen Codes kann [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] sich das Engineering-Team auf eine zusätzliche Sicherheitsanalyse und Quell Code Verwaltung für den sicherheitskritischen Kernel konzentrieren, der oberhalb und über den standardmäßigen Sicherheitsverfahren liegt (siehe [WPF-Sicherheitsstrategie-Sicherheit). Engineering](wpf-security-strategy-security-engineering.md)).  
  
 Beachten Sie, dass .NET Framework vertrauenswürdigen Code ermöglicht, den XBAP-Internet Zonen-Sandkasten zu erweitern, indem Sie Entwicklern <xref:System.Security.AllowPartiallyTrustedCallersAttribute> das Schreiben verwalteter Assemblys ermöglichen, die mit (APTCA) markiert sind und im globalen Assemblycache des Benutzers bereitgestellt werden. Das Kennzeichnen einer Assembly mit dem APTCA-Attribut ist ein extrem kritischer Sicherheitsvorgang, da jeder Code, auch bösartiger Code aus dem Internet, diese Assembly aufrufen kann. Bei diesem Vorgang sind äußerste Vorsicht und die Verwendung bewährter Methoden ein absolutes Muss. Die Benutzer müssen zuerst angeben, dass sie dieser Software vertrauen, bevor sie installiert werden kann.  
  
<a name="Microsoft_Internet_Explorer_Security"></a>   
## <a name="microsoft-internet-explorer-security"></a>Microsoft Internet Explorer-Sicherheit  
 Neben Funktionen zum Reduzieren von Sicherheitsproblemen und zum Vereinfachen der Sicherheitskonfiguration enthält [!INCLUDE[TLA#tla_ie6sp2](../../../includes/tlasharptla-ie6sp2-md.md)] verschiedene Features, die die Sicherheit für die Benutzer von [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../includes/tlasharptla-winfxwebappsharpplural-md.md)] noch weiter erhöhen. Hauptziel dieser Features ist eine bessere Kontrolle des Benutzers über seine Arbeit im Brower.  
  
 Vor [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] mussten Benutzer mit Folgendem rechnen:  
  
- Zufällige Popupfenster  
  
- Verwirrende Skriptumleitung  
  
- Zahlreiche Sicherheitsdialogfelder auf manchen Websites  
  
 In einigen Fällen würden nicht vertrauenswürdige Websites versuchen, Benutzer zu täuschen, indem Sie die Installation [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] Spoofing oder wiederholt ein Microsoft ActiveX-Installations Dialogfeld angezeigt werden, auch wenn der Benutzer Sie möglicherweise abgebrochen hat. Mit diesen Techniken ist es möglich, eine große Anzahl von Benutzern zu schlechten Entscheidungen zu verleiten, die zur Installation von Spyware-Anwendungen führen.  
  
 [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] enthält mehrere Features, um diese Art von Problemen rund um das Prinzip der Benutzerinitiierung zu minimieren. [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)]erkennt, wenn ein Benutzer vor einer Aktion, die als *Benutzer Initiierung*bezeichnet wird, auf ein Link oder ein Seitenelement geklickt hat, und behandelt es anders, als wenn eine ähnliche Aktion stattdessen durch das Skript auf einer Seite ausgelöst wird. Beispielsweise enthält einen [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] **Popup Blocker** , der erkennt, wenn ein Benutzer auf eine Schaltfläche klickt, bevor auf der Seite ein Popup erstellt wird. Auf diese Weise kann [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] die meisten unschädlichen Popups zulassen und gleichzeitig die Popups verhindern, die Benutzer weder anfordern noch wünschen. Blockierte Popups werden unter der neuen **Informationsleiste**erfasst, sodass der Benutzer den Block manuell überschreiben und das Popup anzeigen kann.  
  
 Die gleiche Benutzer Initiierungs Logik wird auch für **geöffnete**/Sicherheits Aufforderungen zum**Speichern** verwendet. ActiveX-Installations Dialogfelder werden immer unter der Informationsleiste erfasst, es sei denn, Sie stellen ein Upgrade von einem zuvor installierten Steuerelement dar. All diese Maßnahmen sorgen für eine Benutzererfahrung mit mehr Sicherheit und Kontrolle und bieten Schutz vor Websites, die den Benutzer belästigen und zur Installation von unerwünschter oder schädlicher Software verleiten wollen.  
  
 Diese Funktionen schützen auch die Kunden, die mit [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] zu Websites wechseln, auf denen sie [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen herunterladen und installieren können. Hauptgrund dafür ist die bessere Benutzererfahrung, die [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] ermöglicht und die weniger Gelegenheit zum Installieren schädlicher oder undurchsichtiger Anwendungen bietet, und zwar ungeachtet der zum Erstellen verwendeten Technologie (einschließlich [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]). [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] erweitert durch die Verwendung von [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] diese Schutzmaßnahmen noch und vereinfacht damit das Herunterladen der zugehörigen Anwendungen über das Internet. Da [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../includes/tlasharptla-winfxwebappsharpplural-md.md)] innerhalb eines Sicherheitssandkastens der Internetzone ausgeführt werden, können sie nahtlos gestartet werden. Andererseits setzen eigenständige [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen volle Vertrauenswürdigkeit voraus, um ausgeführt werden zu können. Für diese Anwendungen zeigt [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] beim Startvorgang ein Sicherheitsdialogfeld an, um auf die Verwendung der zusätzlichen Sicherheitsanforderungen der Anwendung hinzuweisen. Da dies vom Benutzer initiiert werden muss, unterliegt der Vorgang außerdem der Benutzerinitiierungslogik und kann kann abgebrochen werden.  
  
 Im Rahmen unseres stetigen Engagements für die Sicherheit enthält [!INCLUDE[TLA2#tla_ie7](../../../includes/tla2sharptla-ie7-md.md)] die Sicherheitsfunktionen von [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] und erweitert diese noch.  
  
## <a name="see-also"></a>Siehe auch

- [Codezugriffssicherheit](../misc/code-access-security.md)
- [Sicherheit](security-wpf.md)
- [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](wpf-partial-trust-security.md)
- [WPF-Sicherheitsstrategie – Sicherheitsentwicklung](wpf-security-strategy-security-engineering.md)
