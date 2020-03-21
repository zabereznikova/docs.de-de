---
title: Plattformsicherheitsstrategie
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
ms.openlocfilehash: 258fcd7c51ea59de03fe60a4eeb9a82dd1c7efca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174601"
---
# <a name="wpf-security-strategy---platform-security"></a>WPF-Sicherheitsstrategie – Plattformsicherheit
Windows Presentation Foundation (WPF) bietet zwar eine Vielzahl von Sicherheitsdiensten, nutzt aber auch die Sicherheitsfeatures der zugrunde liegenden Plattform, zu der das Betriebssystem, die CLR und Internet Explorer gehören. Diese Ebenen bieten WPF ein starkes, tiefgründiges Sicherheitsmodell, das versucht, einen einzelnen Fehlerpunkt zu vermeiden, wie in der folgenden Abbildung dargestellt:  
  
 ![Diagramm, das das WPF-Sicherheitsmodell anzeigt.](./media/wpf-security-strategy-platform-security/windows-presentation-foundation-security.png)  
  
 Im weiteren Verlauf dieses Themas werden die Features in den einzelnen Layern erläutert, die sich speziell auf WPF beziehen.  

## <a name="operating-system-security"></a>Sicherheit des Betriebssystems  
Das Herzstück von Windows bietet mehrere Sicherheitsfeatures, die die Sicherheitsgrundlage für alle Windows-Anwendungen bilden, einschließlich der mit WPF erstellten. In diesem Thema wird die Breite dieser Sicherheitsfeatures erläutert, die für WPF wichtig sind, sowie die Integration von WPF in diese, um eine weitere tiefen Verteidigungsabwehr bereitzustellen.  
  
### <a name="microsoft-windows-xp-service-pack-2-sp2"></a>Microsoft Windows XP Service Pack 2 (SP2)  
 Zusätzlich zu einer allgemeinen Überprüfung und Stärkung von Windows gibt es drei wichtige Funktionen von Windows XP SP2, die wir in diesem Thema besprechen werden:  
  
- /GS-Kompilierung  
  
- Microsoft Windows Update.  
  
#### <a name="gs-compilation"></a>/GS-Kompilierung  
 Windows XP SP2 bietet Schutz, indem viele Kernsystembibliotheken neu kompiliert werden, einschließlich aller WPF-Abhängigkeiten wie der CLR, um Pufferüberläufe zu verringern. Dies wird mit dem /GS-Parameter und dem C/C++-Befehlszeilencompiler erreicht. Obwohl Pufferüberläufe ausdrücklich vermieden werden sollten, ist die Kompilierung mit /GS ein Beispiel für eine tiefgreifende Verteidigungsmaßnahme gegen potenzielle Sicherheitslücken, die versehentlich oder böswillig durch Pufferüberläufe erzeugt werden.  
  
 In der Vergangenheit waren Pufferüberläufe die Ursache für viele Sicherheitslücken mit gravierenden Folgen. Ein Pufferüberlauf tritt auf, wenn ein Angreifer die Sicherheitsanfälligkeit eines Codes nutzt, die das Einfügen von schädlichem Code ermöglicht, der über die Begrenzungen eines Puffers schreibt. Ein Angreifer kann dann durch Überschreiben der Rückgabeadresse einer Funktion den Prozess, in dem der Code ausgeführt wird, hacken und die Ausführung des Angreifercodes auslösen. Daraus entsteht bösartiger Code, der beliebigen Code mit den gleichen Berechtigungen wie der gehackte Prozess ausführt.  
  
 Auf hoher Ebene schützt das Compilerflag -GS vor möglichen Pufferüberläufen, indem es ein spezielles Sicherheitscookie einfügt, um die Rückgabeadresse einer Funktion zu schützen, die über lokale Zeichenfolgenpuffer verfügt. Nach der Rückgabe einer Funktion wird das Sicherheitscookie mit seinem vorherigen Wert verglichen. Hat sich der Wert geändert, ist möglicherweise ein Pufferüberlauf aufgetreten, und der Prozess wird mit einer Fehlerbedingung beendet. Das Beenden des Prozesses verhindert die Ausführung von potenziell bösartigem Code. Weitere Informationen finden Sie unter [-GS (Buffer Security Check).](/cpp/build/reference/gs-buffer-security-check)  
  
 WPF wird mit dem /GS-Flag kompiliert, um WPF-Anwendungen eine weitere Verteidigungsebene hinzuzufügen.  
  
### <a name="windows-vista"></a>Windows Vista  
WPF-Benutzer unter Windows Vista profitieren von den zusätzlichen Sicherheitsverbesserungen des Betriebssystems, einschließlich "Least-Privilege User Access", Codeintegritätsprüfungen und Berechtigungsisolierung.  
  
#### <a name="user-account-control-uac"></a>Benutzerkontensteuerung (User Account Control, UAC)  
 Heute werden Windows-Benutzer in der Regel mit Administratorrechten ausgeführt, da viele Anwendungen sie entweder für die Installation oder Ausführung oder beides benötigen. Das Schreiben von Standardanwendungseinstellungen in die Registrierung ist nur ein Beispiel.  
  
 Das Arbeiten mit Administratorrechten bedeutet im Grunde, dass Anwendungen von Prozessen ausgeführt werden, denen Administratorrechte gewährt werden. Das hat Auswirkungen auf die Sicherheit, denn bösartiger Code, der zum Hacken eines mit Administratorrechten ausgeführten Prozesses verwendet wird, übernimmt automatisch dessen Berechtigungen, einschließlich des Zugriffs auf kritische Systemressourcen.  
  
 Anwendungen nur mit den unbedingt erforderlichen Berechtigungen auszuführen, ist eine Möglichkeit, sich vor dieser Sicherheitsbedrohung zu schützen. Dies wird als das Prinzip der geringsten Berechtigungen bezeichnet und ist ein Kernmerkmal des Windows-Betriebssystems. Diese Funktion wird als Benutzerkontensteuerung (User Account Control, UAC) bezeichnet und wird von Windows UAC auf zwei wichtige Arten verwendet:  
  
- Die meisten Anwendungen werden standardmäßig mit den Rechten der Benutzerkontensteuerung ausgeführt, selbst wenn der Benutzer ein Administrator ist; nur Anwendungen, die Administratorrechte benötigen, werden mit Administratorrechten ausgeführt. Um mit Administratorrechten ausgeführt zu werden, müssen Anwendungen entweder in ihrem Anwendungsmanifest oder als Eintrag in der Sicherheitsrichtlinie besonders gekennzeichnet werden.  
  
- Bereitstellen von Kompatibilitätslösungen wie die Virtualisierung. Viele Anwendungen versuchen beipielsweise, in eingeschränkte Speicherorte wie "C:\Programme" zu schreiben. Für Anwendungen, die über die Benutzerkontensteuerung ausgeführt werden, steht ein alternativer benutzerbezogener Speicherort zur Verfügung, der für Schreibvorgänge keine Administratorrechte erfordert. Für Anwendungen, die über die Benutzerkontensteuerung ausgeführt werden, wird "C:\Programme" virtualisiert. Dadurch wird der Anschein erweckt, dass die Anwendungen in dieses Verzeichnis schreiben, obwohl sie stattdessen in den alternativen, benutzerbezogenen Speicherort schreiben. Dank dieser Art von Kompatibilität kann das Betriebssystem viele Anwendungen ausführen, die zuvor nicht mit der Benutzerkontensteuerung ausgeführt werden konnten.  
  
#### <a name="code-integrity-checks"></a>Integritätsprüfungen für Code  
 Windows Vista enthält tiefergehende Codeintegritätsprüfungen, um zu verhindern, dass bösartiger Code zur Lade-/Laufzeit in Systemdateien oder in den Kernel eingefügt wird. Dies geht über den Schutz der Systemdateien hinaus.  

### <a name="limited-rights-process-for-browser-hosted-applications"></a>Prozess mit eingeschränkten Rechten für im Browser gehostete Anwendungen  
 Browser-gehostete WPF-Anwendungen werden in der Sandbox der Internetzone ausgeführt. Die WPF-Integration mit Microsoft Internet Explorer erweitert diesen Schutz um zusätzliche Unterstützung.  
  
 Da XAML-Browseranwendungen (XBAPs) im Allgemeinen vom Berechtigungssatz für die Internetzone sandkastenweise festgelegt werden, schadet das Entfernen dieser Berechtigungen XAML-Browseranwendungen (XBAPs) aus Kompatibilitätssicht nicht. Stattdessen wird eine zusätzliche Defense-in-Depth-Ebene geschaffen. Wenn eine in einem Sicherheitssandkasten ausgeführte Anwendung in der Lage ist, andere Ebenen anzugreifen und den Prozess zu hacken, verfügt auch der Prozess nur über eingeschränkte Berechtigungen.  
  
 Weitere Informationen finden [Sie unter Verwenden eines Benutzerkontos mit den geringsten Berechtigungen](https://docs.microsoft.com/previous-versions/tn-archive/cc700846%28v=technet.10%29).  
  
## <a name="common-language-runtime-security"></a>Common Language Runtime-Sicherheit  
 Die Common Language Runtime (CLR) bietet eine Reihe wichtiger Sicherheitsvorteile, darunter Validierung und Überprüfung, Code Zugriffssicherheit (Code Access Security, CAS) und die sicherheitskritische Methodik.  

### <a name="validation-and-verification"></a>Validierung und Prüfung  
 Um Assemblyisolation und -integrität zu gewährleisten, verwendet die CLR einen Validierungsprozess. Die CLR-Validierung stellt sicher, dass Assemblys isoliert werden, indem ihr PE-Dateiformat (Portable Executable) für Adressen überprüft wird, die außerhalb der Assembly verweisen. Die CLR-Validierung überprüft auch die Integrität der Metadaten, die in eine Assembly eingebettet sind.  
  
 Um die Typsicherheit zu gewährleisten, häufige Sicherheitsprobleme (z. B. Pufferüberläufe) zu vermeiden und Sandboxing durch Subprozessisolation zu aktivieren, verwendet CLR security das Konzept der Überprüfung.  
  
 Verwaltete Anwendungen werden in Microsoft Intermediate Language (MSIL) kompiliert. Wenn Methoden in einer verwalteten Anwendung ausgeführt werden, wird die MSIL über Just-in-Time (JIT)-Kompilierung in systemeigenen Code kompiliert. Die JIT-Kompilierung enthält einen Prüfprozess mit vielen Sicherheits- und Stabilitätsregeln, die sicherstellen, dass der Code keine der folgenden Eigenschaften aufweist:  
  
- Verletzen von Typverträgen  
  
- Verursachen von Pufferüberläufen  
  
- Unkontrollierter Zugriff auf den Arbeitsspeicher  
  
 Verwalteter Code, der den Prüfregeln nicht entspricht, darf nur dann ausgeführt werden, wenn er als vertrauenswürdiger Code gilt.  
  
 Der Vorteil von überprüfbarem Code ist ein Hauptgrund, warum WPF auf .NET Framework aufbaut. Mit zunehmender Verwendung prüfbaren Codes sinkt die Wahrscheinlichkeit, dass potenzielle Schwachstellen ausgenutzt werden, ganz erheblich.  
  
### <a name="code-access-security"></a>Codezugriffssicherheit  
 Ein Clientcomputer stellt eine Vielzahl von Ressourcen bereit, auf die eine verwaltete Anwendung zugreifen kann. Dazu zählen u. a. Dateisystem, Registrierung, Druckdienste, Benutzeroberfläche, Reflektion und Umgebungsvariablen. Bevor eine verwaltete Anwendung auf eine der Ressourcen auf einem Clientcomputer zugreifen kann, muss sie dazu über die Berechtigung .NET Framework verfügen. Eine Berechtigung in CAS ist <xref:System.Security.CodeAccessPermission>eine Unterklasse der ; CAS implementiert eine Unterklasse für jede Ressource, auf die verwaltete Anwendungen zugreifen können.  
  
 Der Satz von Berechtigungen, die einer verwalteten Anwendung von CAS gewährt werden, wenn sie mit der Ausführung beginnt, wird als Berechtigungssatz bezeichnet und wird durch Die von der Anwendung bereitgestellte Beweise bestimmt. Bei WPF-Anwendungen wird der angegebene Beweis für den Speicherort oder die Zone bereitgestellt, von der aus die Anwendungen gestartet werden. CAS identifiziert die folgenden Zonen:  
  
- **Mein Computer**. Anwendungen, die auf dem Clientcomputer gestartet werden (voll vertrauenswürdig).  
  
- **Lokales Intranet**. Anwendungen, die aus dem Intranet gestartet werden (in gewisser Weise vertrauenswürdig).  
  
- **Internet**. Anwendungen, die aus dem Internet gestartet werden (wenig vertrauenswürdig).  
  
- **Vertrauenswürdige Sites**. Anwendungen, die von einem Benutzer als vertrauenswürdig identifiziert wurden (wenig vertrauenswürdig).  
  
- **Nicht vertrauenswürdige Sites**. Anwendungen, die von einem Benutzer als nicht vertrauenswürdig identifiziert wurden (nicht vertrauenswürdig).  
  
 Für jede dieser Zonen stellt CAS einen vordefinierten Berechtigungssatz bereit, der die Berechtigungen enthält, die der jeweiligen Vertrauensstufe entsprechen. Dazu gehören:  
  
- **FullTrust**. Für Anwendungen, die aus der Zone **"Mein Computer"** gestartet werden. Alle möglichen Berechtigungen werden gewährt.  
  
- **LocalIntranet**. Für Anwendungen, die aus der lokalen **Intranetzone** gestartet werden. Für einen moderaten Zugriff auf die Ressourcen des Clientcomputers wird eine Teilmenge von Berechtigungen gewährt. Dazu zählen isolierter Speicher, uneingeschränkter Zugriff auf die Benutzeroberfläche und Dateidialogfelder, eingeschränkte Reflektion sowie eingeschränkter Zugriff auf Umgebungsvariablen. Berechtigungen für kritische Ressourcen wie die Registrierung werden nicht bereitgestellt.  
  
- **Internet**. Für Anwendungen, die aus der **Zone "Internet"** oder **"Vertrauenswürdige Sites"** gestartet werden. Für einen eingeschränkten Zugriff auf die Ressourcen des Clientcomputers wird eine Teilmenge von Berechtigungen gewährt. Dazu zählen isolierter Speicher, Öffnen von Dateien sowie eingeschränkter Zugriff auf die Benutzeroberfläche. Im Wesentlichen isoliert dieser Berechtigungssatz Anwendungen vom Clientcomputer.  
  
 Anwendungen, die aus der Zone **"Nicht vertrauenswürdige Sites"** stammen, werden von CAS überhaupt keine Berechtigungen erteilt. Daher gibt es für diese Anwendungen keinen vordefinierten Berechtigungssatz.  
  
 Die folgende Abbildung veranschaulicht die Beziehung zwischen Zonen, Berechtigungssätzen, Berechtigungen und Ressourcen:  
  
 ![Diagramm, das CAS-Berechtigungssätze anzeigt.](./media/wpf-security-strategy-platform-security/code-access-security-permissions-relationship.png)  
  
 Die Einschränkungen der Sicherheitssandbox für die Internetzone gelten gleichermaßen für jeden Code, den ein XBAP aus einer Systembibliothek importiert, einschließlich WPF. Dadurch wird sichergestellt, dass jedes Bit des Codes gesperrt ist, sogar WPF. Leider muss ein XBAP, um ausgeführt werden zu können, Funktionen ausführen, die mehr Berechtigungen erfordern als die, die von der Sicherheits-Sandbox für die Internetzone aktiviert sind.  
  
 Betrachten Sie eine XBAP-Anwendung, die die folgende Seite enthält:  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Um diesen XBAP auszuführen, muss der zugrunde liegende WPF-Code mehr Funktionen ausführen, als für den aufrufenden XBAP verfügbar sind, einschließlich:  
  
- Erstellen eines Fensterhandles (HWND) zum Rendern  
  
- Verteilen von Nachrichten  
  
- Laden der Schriftart Tahoma  
  
 Unter dem Gesichtspunkt der Sicherheit wäre die Gewährung des direkten Zugriffs auf diese Vorgänge für die im Sicherheitssandkasten ausgeführte Anwendung eine Katastrophe.  
  
 Glücklicherweise erfüllt WPF diese Situation, indem es diesen Vorgängen erlaubt, diese Vorgänge mit erhöhten Berechtigungen im Namen der Sandkastenanwendung auszuführen. Während alle WPF-Vorgänge mit den eingeschränkten Sicherheitsberechtigungen der Anwendungsdomäne des XBAP in der Internetzone überprüft werden, wird WPF (wie bei anderen Systembibliotheken) ein Berechtigungssatz gewährt, der alle möglichen Berechtigungen enthält.
  
 Dies erfordert, dass WPF erhöhte Berechtigungen erhält, während verhindert wird, dass diese Berechtigungen vom Berechtigungssatz für die Internetzone der Hostanwendungsdomäne verwaltet werden.  
  
 WPF verwendet die **Assert-Methode** einer Berechtigung. Der folgende Code beschreibt die Vorgehensweise.  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 **Der Assert** verhindert im Wesentlichen, dass die von WPF erforderlichen unbegrenzten Berechtigungen durch die Internetzonenberechtigungen des XBAP eingeschränkt werden.  
  
 Aus Plattformsicht ist WPF für die korrekte Verwendung von **Assert** verantwortlich. Eine falsche Verwendung von **Assert** könnte böswilligen Code in die Lage versetzen, Berechtigungen zu erhöhen. Daher ist es wichtig, **Assert** nur bei Bedarf aufzurufen und sicherzustellen, dass die Sandbox-Einschränkungen intakt bleiben. Beispielsweise darf im Sicherheitssandkasten ausgeführter Code zwar keine beliebigen Dateien öffnen, aber Schriftarten verwenden. WPF ermöglicht sandkastened Anwendungen die Verwendung von Schriftartfunktionalität durch Aufrufen von **Assert**, und für WPF, um Dateien zu lesen, von denen bekannt ist, dass sie diese Schriftarten im Namen der Sandkastenanwendung enthalten.  
  
### <a name="clickonce-deployment"></a>ClickOnce-Bereitstellung  
 ClickOnce ist eine umfassende Bereitstellungstechnologie, die in .NET Framework enthalten ist und in Visual Studio integriert ist (detaillierte Informationen finden Sie unter [ClickOnce-Sicherheit und -Bereitstellung).](/visualstudio/deployment/clickonce-security-and-deployment) Eigenständige WPF-Anwendungen können mit ClickOnce bereitgestellt werden, während browsergehostete Anwendungen mit ClickOnce bereitgestellt werden müssen.  
  
 Anwendungen, die mit ClickOnce bereitgestellt werden, erhalten eine zusätzliche Sicherheitsschicht über Code Access Security (CAS); Im Wesentlichen fordern von ClickOnce bereitgestellte Anwendungen die erforderlichen Berechtigungen an. Diese Berechtigungen werden nur gewährt, wenn sie nicht höher sind als die Berechtigungen im Berechtigungssatz für die Zone, von der die Anwendung bereitgestellt wird. Durch Die Reduzierung des Satzes von Berechtigungen auf die erforderlichen Berechtigungen, selbst wenn sie kleiner sind als die vom Berechtigungssatz der Startzone bereitgestellten Berechtigungen, wird die Anzahl der Ressourcen, auf die die Anwendung Zugriff hat, auf ein absolutes Minimum reduziert. Dadurch wird der mögliche Schaden für den Clientcomputer reduziert, falls die Anwendung gehackt wird.  
  
### <a name="security-critical-methodology"></a>Sicherheitsrelevante Methode  
 Der WPF-Code, der Berechtigungen zum Aktivieren der Internetzonen-Sandbox für XBAP-Anwendungen verwendet, muss so weit wie möglich an Sicherheitsüberwachung und -steuerung gehalten werden. Um diese Anforderung zu erleichtern, bietet .NET Framework neue Unterstützung für die Verwaltung von Code, der Berechtigungen erhöht. Insbesondere können Sie mit der CLR Code identifizieren, der Berechtigungen <xref:System.Security.SecurityCriticalAttribute>erhöht, und ihn mit der markieren. Jeder Code, <xref:System.Security.SecurityCriticalAttribute> der nicht mit dieser Methode gekennzeichnet *ist,* wird transparent. Umgekehrt wird verhindert, dass verwalteter Code, der nicht mit dem <xref:System.Security.SecurityCriticalAttribute> gekennzeichnet ist, die Rechte erhöht.  
  
 Die sicherheitskritische Methode ermöglicht die Organisation von WPF-Code, der Berechtigungen in *einen sicherheitskritischen Kernel*erhebt, wobei der Rest transparent ist. Die Isolierung des sicherheitskritischen Codes ermöglicht es dem WPF-Engineering-Team, eine zusätzliche Sicherheitsanalyse und Quellcodeverwaltung auf den sicherheitskritischen Kernel über die Standardsicherheitspraktiken hinaus zu fokussieren (siehe [WPF Security Strategy - Security Engineering](wpf-security-strategy-security-engineering.md)).  
  
 Beachten Sie, dass .NET Framework vertrauenswürdigen Code zum Erweitern der XBAP-Internetzonen-Sandbox zulässt, indem Entwickler verwaltete Assemblys schreiben können, die mit <xref:System.Security.AllowPartiallyTrustedCallersAttribute> APTCA markiert und im globalen Assemblycache (GAC) des Benutzers bereitgestellt werden. Das Kennzeichnen einer Assembly mit dem APTCA-Attribut ist ein extrem kritischer Sicherheitsvorgang, da jeder Code, auch bösartiger Code aus dem Internet, diese Assembly aufrufen kann. Bei diesem Vorgang sind äußerste Vorsicht und die Verwendung bewährter Methoden ein absolutes Muss. Die Benutzer müssen zuerst angeben, dass sie dieser Software vertrauen, bevor sie installiert werden kann.  
  
## <a name="microsoft-internet-explorer-security"></a>Microsoft Internet Explorer-Sicherheit  
 Neben der Reduzierung von Sicherheitsproblemen und der Vereinfachung der Sicherheitskonfiguration enthält Microsoft Internet Explorer 6 (SP2) mehrere Funktionen, die die Sicherheit für Benutzer von XAML-Browseranwendungen (XBAPs) erhöhen. Hauptziel dieser Features ist eine bessere Kontrolle des Benutzers über seine Arbeit im Brower.  
  
 Vor IE6 SP2 können Benutzer einer der folgenden Optionen unterliegen:  
  
- Zufällige Popupfenster  
  
- Verwirrende Skriptumleitung  
  
- Zahlreiche Sicherheitsdialogfelder auf manchen Websites  
  
 In einigen Fällen würden nicht vertrauenswürdige Websites versuchen, Benutzer [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] zu betrügen, indem sie die Installation vortun oder wiederholt ein Microsoft ActiveX-Installationsdialogfeld anzeigen, obwohl der Benutzer es möglicherweise abgebrochen hat. Mit diesen Techniken ist es möglich, eine große Anzahl von Benutzern zu schlechten Entscheidungen zu verleiten, die zur Installation von Spyware-Anwendungen führen.  
  
 IE6 SP2 enthält mehrere Funktionen, um diese Art von Problemen zu mildern, die sich um das Konzept der Benutzerinitiierung drehen. IE6 SP2 erkennt, wenn ein Benutzer vor einer Aktion auf einen Link oder ein Seitenelement geklickt hat, das als *Benutzerinitiierung*bezeichnet wird, und behandelt ihn anders, als wenn eine ähnliche Aktion stattdessen durch das Skript auf einer Seite ausgelöst wird. Beispielsweise enthält IE6 SP2 einen **Popupblocker,** der erkennt, wenn ein Benutzer auf eine Schaltfläche klickt, bevor die Seite ein Pop-up erstellt. Dadurch kann IE6 SP2 die meisten harmlosen Pop-ups zulassen und gleichzeitig Pop-ups verhindern, die Benutzer weder verlangen noch wünschen. Blockierte Pop-ups werden unter der neuen **Informationsleiste**gefangen, die es dem Benutzer ermöglicht, den Block manuell zu überschreiben und das Pop-up anzuzeigen.  
  
 Dieselbe Benutzerinitiierungslogik wird auch auf Sicherheitsaufforderungen zum **Öffnen**/**Save** von Speichern angewendet. ActiveX-Installationsdialogfelder werden immer unter der Informationsleiste abgefangen, es sei denn, sie stellen ein Upgrade von einem zuvor installierten Steuerelement dar. All diese Maßnahmen sorgen für eine Benutzererfahrung mit mehr Sicherheit und Kontrolle und bieten Schutz vor Websites, die den Benutzer belästigen und zur Installation von unerwünschter oder schädlicher Software verleiten wollen.  
  
 Diese Funktionen schützen kunden, die IE6 SP2 verwenden, um zu Websites zu navigieren, auf denen sie WPF-Anwendungen herunterladen und installieren können. Dies liegt insbesondere daran, dass IE6 SP2 eine bessere Benutzererfahrung bietet, die die Wahrscheinlichkeit verringert, dass Benutzer bösartige oder hinterhältige Anwendungen installieren, unabhängig davon, welche Technologie zum Erstellen verwendet wurde, einschließlich WPF. WPF ergänzt diese Schutzmaßnahmen, indem ClickOnce verwendet wird, um das Herunterladen seiner Anwendungen über das Internet zu erleichtern. Da XAML-Browseranwendungen (XBAPs) in einer Sicherheitssandbox für die Internetzone ausgeführt werden, können sie nahtlos gestartet werden. Auf der anderen Seite erfordern eigenständige WPF-Anwendungen volle Vertrauenswürdigkeit, um ausgeführt zu werden. Für diese Anwendungen zeigt ClickOnce während des Startvorgangs ein Sicherheitsdialogfeld an, um die Verwendung der zusätzlichen Sicherheitsanforderungen der Anwendung zu benachrichtigen. Da dies vom Benutzer initiiert werden muss, unterliegt der Vorgang außerdem der Benutzerinitiierungslogik und kann kann abgebrochen werden.  
  
 Internet Explorer 7 integriert und erweitert die Sicherheitsfunktionen von IE6 SP2 als Teil eines kontinuierlichen Engagements für Sicherheit.  
  
## <a name="see-also"></a>Weitere Informationen

- [Codezugriffssicherheit](../misc/code-access-security.md)
- [Sicherheit](security-wpf.md)
- [WPF Partial Trust Security](wpf-partial-trust-security.md)
- [WPF-Sicherheitsstrategie – Sicherheitsentwicklung](wpf-security-strategy-security-engineering.md)
