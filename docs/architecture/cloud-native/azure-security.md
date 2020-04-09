---
title: Azure-Sicherheit für cloudnative Apps
description: Architektur von Cloud Native .NET-Apps für Azure | Azure Security für native Cloud-Apps
ms.date: 06/30/2019
ms.openlocfilehash: 13b5ad7a883a83014913fa0a6a020610c28c524f
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989141"
---
# <a name="azure-security-for-cloud-native-apps"></a>Azure-Sicherheit für cloudnative Apps

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Cloud-native Anwendungen können einfacher und schwieriger zu sichern sein als herkömmliche Anwendungen. Auf der anderen Seite müssen Sie mehr kleinere Anwendungen sichern und mehr Energie für den Aufbau der Sicherheitsinfrastruktur aufwenden. Die Heterogenität der Programmiersprachen und -stile in den meisten Dienstbereitstellungen bedeutet auch, dass Sie den Security Bulletins vieler verschiedener Anbieter mehr Aufmerksamkeit schenken müssen.

Auf der anderen Seite begrenzen kleinere Dienste, die jeweils über einen eigenen Datenspeicher verfügen, den Umfang eines Angriffs. Wenn ein Angreifer ein System kompromittiert, ist es für den Angreifer wahrscheinlich schwieriger, den Sprung zu einem anderen System zu machen, als es in einer monolithischen Anwendung der Fall ist. Prozessgrenzen sind starke Grenzen. Wenn eine Datenbanksicherung ausläuft, ist der Schaden außerdem begrenzter, da diese Datenbank nur eine Teilmenge von Daten enthält und wahrscheinlich keine personenbezogenen Daten enthält.

## <a name="threat-modeling"></a>Bedrohungsmodellierung

Egal, ob die Vorteile die Nachteile von Cloud-nativen Anwendungen überwiegen, die gleiche ganzheitliche Sicherheitsmentalität muss beachtet werden. Sicherheit und sicheres Denken müssen Teil jedes Schritts der Entwicklungs- und Betriebsgeschichte sein. Bei der Planung einer Anwendung stellen Sie Fragen wie:

- Welche Auswirkungen würde der Verlust dieser Daten haben?
- Wie können wir den Schaden begrenzen, der durch fehlerhafte Daten verursacht wird, die in diesen Dienst injiziert werden?
- Wer sollte Zugriff auf diese Daten haben?
- Gibt es Prüfungsrichtlinien rund um den Entwicklungs- und Freigabeprozess?

Alle diese Fragen sind Teil eines Prozesses namens [Bedrohungsmodellierung](https://docs.microsoft.com/azure/security/azure-security-threat-modeling-tool). Dieser Prozess versucht, die Frage zu beantworten, welche Bedrohungen es für das System gibt, wie wahrscheinlich die Bedrohungen sind und welche potenziellen Schäden dadurch entstehen.

Sobald die Liste der Bedrohungen erstellt wurde, müssen Sie entscheiden, ob sie es wert sind, zu mildern. Manchmal ist eine Bedrohung so unwahrscheinlich und teuer zu planen, dass es sich nicht lohnt, Energie dafür auszugeben. Beispielsweise könnte ein Akteur auf staatlicher Ebene Änderungen in das Design eines Prozesses einfügen, der von Millionen von Geräten verwendet wird. Anstatt nun einen bestimmten Codeinder in [Ring 3](https://en.wikipedia.org/wiki/Protection_ring)auszuführen, wird dieser Code in Ring 0 ausgeführt. Dies ermöglicht einen Exploit, der den Hypervisor umgehen und den Angriffscode auf den Bare-Metal-Computern ausführen kann, und ermöglicht Angriffe auf alle virtuellen Maschinen, die auf dieser Hardware ausgeführt werden.

Die veränderten Prozessoren sind ohne Mikroskop und fortgeschrittene Kenntnisse über das Silizium-Design dieses Prozessors schwer zu erkennen. Dieses Szenario ist unwahrscheinlich und teuer zu mildern, so dass wahrscheinlich kein Bedrohungsmodell würde empfehlen, Exploit-Schutz für sie zu bauen.

Wahrscheinlichere Bedrohungen, wie z. `Id` B. fehlerhafte Zugriffskontrollen, die inkrementelle Angriffe (ersetzen `Id=2` durch `Id=3` in der URL) oder SQL-Injektion ermöglichen, sind attraktiver, um Schutz zu erstellen. Die Abschwächungen für diese Bedrohungen sind durchaus vernünftig zu bauen und zu verhindern peinliche Sicherheitslücken, die den Ruf des Unternehmens zu schmieren.

## <a name="principle-of-least-privilege"></a>Prinzip der geringsten Rechte

Eine der Gründungsideen in der Computersicherheit ist das Prinzip des geringsten Privilegs (POLP). Es ist eigentlich eine grundlegende Idee in den meisten jede Form von Sicherheit, sei es digital oder physisch. Kurz gesagt, das Prinzip ist, dass jeder Benutzer oder Prozess über die geringste Anzahl von Rechten verfügen sollte, die für die Ausführung seiner Aufgabe möglich sind.

Denken Sie beispielsweise an die Kassenprüfer einer Bank: Der Zugang zum Tresor ist eine ungewöhnliche Aktivität. Also, der durchschnittliche Erzähler kann den Safe nicht selbst öffnen. Um Zugriff zu erhalten, müssen sie ihre Anforderung über einen Bankmanager eskalieren, der zusätzliche Sicherheitsüberprüfungen durchführt.

In einem Computersystem sind ein fantastisches Beispiel die Rechte eines Benutzers, der eine Verbindung zu einer Datenbank herstellt. In vielen Fällen gibt es ein einzelnes Benutzerkonto, das sowohl zum Erstellen der Datenbankstruktur als auch zum Ausführen der Anwendung verwendet wird. Außer in extremen Fällen benötigt das Konto, auf dem die Anwendung ausgeführt wird, nicht die Möglichkeit, Schemainformationen zu aktualisieren. Es sollten mehrere Konten vorhanden sein, die unterschiedliche Berechtigungsebenen bereitstellen. Die Anwendung sollte nur die Berechtigungsstufe verwenden, die Lese- und Schreibzugriff auf die Daten in den Tabellen gewährt. Diese Art von Schutz würde Angriffe eliminieren, die darauf abzielten, Datenbanktabellen zu löschen oder böswillige Trigger einzuführen.

Fast jeder Teil des Erstellens einer Cloud-nativen Anwendung kann davon profitieren, sich an das Prinzip der geringsten Berechtigungen zu erinnern. Sie finden es im Spiel beim Einrichten von Firewalls, Netzwerksicherheitsgruppen, Rollen und Bereichen in der rollenbasierten Zugriffssteuerung (RBAC).

## <a name="penetration-testing"></a>Penetrationstests

Mit zunehmender Geschwindigkeit von Anwendungen steigt die Anzahl der Angriffsvektoren. Die Bedrohungsmodellierung ist insofern fehlerhaft, als sie tendenziell von denselben Personen ausgeführt wird, die das System erstellen. Auf die gleiche Weise, wie viele Entwickler Schwierigkeiten haben, sich Benutzerinteraktionen vorzustellen und dann unbrauchbare Benutzeroberflächen zu erstellen, haben die meisten Entwickler Schwierigkeiten, jeden Angriffsvektor zu sehen. Es ist auch möglich, dass die Entwickler, die das System bauen, nicht gut in Angriffsmethoden versiert sind und etwas Entscheidendes verpassen.

Penetrationstests oder "Stifttests" beinhalten das Einziehen externer Akteure, um zu versuchen, das System anzugreifen. Bei diesen Angreifern kann es sich um ein externes Beratungsunternehmen oder andere Entwickler mit guten Sicherheitskenntnissen aus einem anderen Teil des Unternehmens handeln. Sie erhalten einen Freibrief, um zu versuchen, das System zu untergraben. Häufig finden sie umfangreiche Sicherheitslücken, die gepatcht werden müssen. Manchmal ist der Angriffsvektor etwas völlig Unerwartetes wie die Ausnutzung eines Phishing-Angriffs gegen den CEO.

Azure selbst wird ständig von einem [Hackerteam innerhalb von Microsoft](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/)angegriffen. Im Laufe der Jahre waren sie die ersten, die Dutzende potenziell katastrophaler Angriffsvektoren gefunden und geschlossen haben, bevor sie extern ausgenutzt werden können. Je verlockender ein Ziel ist, desto wahrscheinlicher ist es, dass ewige Akteure versuchen, es auszunutzen, und es gibt ein paar Ziele auf der Welt, die verlockender sind als Azure.

## <a name="monitoring"></a>Überwachung

Sollte ein Angreifer versuchen, in eine Anwendung einzudringen, sollte davor gewarnt werden. Häufig können Angriffe erkannt werden, indem die Protokolle von Diensten untersucht werden. Angriffe hinterlassen verräterische Zeichen, die entdeckt werden können, bevor sie erfolgreich sind. Beispielsweise stellt ein Angreifer, der versucht, ein Kennwort zu erraten, viele Anforderungen an ein Anmeldesystem. Die Überwachung rund um das Anmeldesystem kann seltsame Muster erkennen, die nicht mit dem typischen Zugriffsmuster in Einklang stehen. Diese Überwachung kann in eine Warnung umgewandelt werden, die wiederum eine Betriebsperson warnen kann, eine Art Gegenmaßnahme zu aktivieren. Ein ausgereiftes Überwachungssystem kann sogar auf der Grundlage dieser Abweichungen maßnahmen, um proaktiv Regeln hinzuzufügen, um Anforderungen zu blockieren oder Antworten zu drosseln.

## <a name="securing-the-build"></a>Sicherung des Builds

Ein Ort, an dem Sicherheit oft übersehen wird, ist der Buildprozess. Der Build sollte nicht nur Sicherheitsüberprüfungen ausführen, z. B. das Scannen nach unsicherem Code oder eingecheckten Anmeldeinformationen, sondern auch der Build selbst sollte sicher sein. Wenn der Buildserver kompromittiert ist, bietet er einen fantastischen Vektor für die Einführung von beliebigem Code in das Produkt.

Stellen Sie sich vor, ein Angreifer möchte die Passwörter von Personen stehlen, die sich bei einer Webanwendung anmelden. Sie könnten einen Buildschritt einführen, der den ausgecheckten Code ändert, um jede Anmeldeanforderung auf einem anderen Server zu spiegeln. Wenn der Code das nächste Mal den Build durchläuft, wird er im Hintergrund aktualisiert. Das Scannen der Quellcode-Sicherheitsanfälligkeit wird dies nicht abfangen, da er vor dem Build ausgeführt wird. Ebenso wird es niemand in einer Codeüberprüfung abfangen, da die Buildschritte auf dem Buildserver leben. Der ausgenutzte Code wird in die Produktion gehen, wo er Passwörter ernten kann. Wahrscheinlich gibt es kein Überwachungsprotokoll für die Änderungen des Buildprozesses oder zumindest niemanden, der die Überwachung überwacht.

Dies ist ein perfektes Beispiel für ein scheinbar niedriges Wertziel, das verwendet werden kann, um in das System einzubrechen. Sobald ein Angreifer den Umfang des Systems durchbricht, kann er damit beginnen, Wege zu finden, um seine Berechtigungen so zu erhöhen, dass er überall, wo er möchte, echten Schaden anrichten kann.

## <a name="building-secure-code"></a>Erstellen sicherer Code

.NET Framework ist bereits ein ziemlich sicheres Framework. Es vermeidet einige der Fallstricke von nicht verwaltetem Code, z. B. das Gehen von den Enden von Arrays. Es wird aktiv daran gearbeitet, Sicherheitslücken zu beheben, wenn sie entdeckt werden. Es gibt sogar ein [Bug-Bounty-Programm,](https://www.microsoft.com/msrc/bounty) das Forscher bezahlt, Probleme im Framework zu finden und sie zu melden, anstatt sie auszunutzen.

Es gibt viele Möglichkeiten, .NET-Code sicherer zu machen. Die Beachtung der Richtlinien, wie z. B. die Richtlinien für die [sichere Codierung für .NET,](https://docs.microsoft.com/dotnet/standard/security/secure-coding-guidelines) ist ein angemessener Schritt, um sicherzustellen, dass der Code von Grund auf sicher ist. Die [OWASP Top 10](https://owasp.org/www-project-top-ten/) ist ein weiterer unschätzbarer Leitfaden zum Erstellen von sicherem Code.

Der Buildprozess ist ein guter Ort, um Scan-Tools zu setzen, um Probleme im Quellcode zu erkennen, bevor sie in die Produktion gelangen. Die meisten Projekte hängen von einigen anderen Paketen ab. Ein Tool, das nach veralteten Paketen suchen kann, wird Probleme in einem nächtlichen Build fangen. Selbst beim Erstellen von Docker-Images ist es nützlich, zu überprüfen und sicherzustellen, dass das Basisabbild keine bekannten Schwachstellen aufweist. Eine andere Sache zu überprüfen ist, dass niemand versehentlich Anmeldeinformationen eingecheckt hat.

## <a name="built-in-security"></a>Integrierte Sicherheit

Azure wurde entwickelt, um die Benutzerfreundlichkeit und Sicherheit für die Mehrheit der Benutzer in Einklang zu bringen. Verschiedene Benutzer haben unterschiedliche Sicherheitsanforderungen, daher müssen sie ihren Ansatz für die Cloudsicherheit optimieren. Microsoft veröffentlicht viele Sicherheitsinformationen im [Trust Center](https://azure.microsoft.com/support/trust-center/). Diese Ressource sollte die erste Anlaufstelle für Fachleute sein, die wissen möchten, wie die integrierten Technologien zur Eindämmung von Angriffen funktionieren.

Innerhalb des Azure-Portals ist der [Azure Advisor](https://azure.microsoft.com/services/advisor/) ein System, das ständig eine Umgebung scannt und Empfehlungen gibt. Einige dieser Empfehlungen sollen Benutzern Geld sparen, andere sind jedoch dazu gedacht, potenziell unsichere Konfigurationen zu identifizieren, z. B. einen Speichercontainer für die Welt offen zu haben und nicht durch ein virtuelles Netzwerk geschützt zu sein.

## <a name="azure-network-infrastructure"></a>Azure-Netzwerkinfrastruktur

In einer lokalen Bereitstellungsumgebung wird viel Energie für den Aufbau von Netzwerken verwendet. Das Einrichten von Routern, Switches und dergleichen ist eine komplizierte Arbeit. Netzwerke ermöglichen es bestimmten Ressourcen, mit anderen Ressourcen zu sprechen und in einigen Fällen den Zugriff zu verhindern. Eine häufige Netzwerkregel besteht darin, den Zugriff auf die Produktionsumgebung aus der Entwicklungsumgebung zu beschränken, da ein halb entwickelter Codevorgang fehlerhaft ausgeführt wird und einen Datenbereich löscht.

Die meisten PaaS Azure-Ressourcen verfügen sofort nur über die einfachste und freizügigste Netzwerkeinrichtung. Beispielsweise kann jeder im Internet auf einen App-Dienst zugreifen. Neue SQL Server-Instanzen werden in der Regel eingeschränkt, sodass externe Parteien nicht darauf zugreifen können, aber die von Azure selbst verwendeten IP-Adressbereiche sind durch zulässig. Während der SQL-Server also vor externen Bedrohungen geschützt ist, muss ein Angreifer nur einen Azure-Bridgehead einrichten, von dem aus er Angriffe auf alle SQL-Instanzen in Azure starten kann.

Glücklicherweise können die meisten Azure-Ressourcen in einem virtuellen Azure-Netzwerk platziert werden, das eine detailliertere Zugriffssteuerung ermöglicht. Ähnlich wie lokale Netzwerke private Netzwerke einrichten, die vor der weiteren Welt geschützt sind, sind virtuelle Netzwerke Inseln mit privaten IP-Adressen, die sich innerhalb des Azure-Netzwerks befinden.

![Abbildung 10-1 Ein virtuelles Netzwerk in Azure](./media/virtual-network.png)
Abbildung**10-1**. Ein virtuelles Netzwerk in Azure.

Auf die gleiche Weise, wie lokale Netzwerke über eine Firewall verfügen, die den Zugriff auf das Netzwerk regelt, können Sie eine ähnliche Firewall an der Grenze des virtuellen Netzwerks einrichten. Standardmäßig können alle Ressourcen in einem virtuellen Netzwerk weiterhin mit dem Internet sprechen. Nur eingehende Verbindungen erfordern eine Art explizite Firewallausnahme.

Wenn das Netzwerk eingerichtet ist, können interne Ressourcen wie Speicherkonten so eingerichtet werden, dass nur Ressourcen, die sich ebenfalls im virtuellen Netzwerk befinden, auf den Zugriff zugreifen können. Diese Firewall bietet ein zusätzliches Maß an Sicherheit, wenn die Schlüssel für dieses Speicherkonto durchgesickert sind, könnten Angreifer keine Verbindung zu ihr herstellen, um die durchgesickerten Schlüssel auszunutzen. Dies ist ein weiteres Beispiel für das Prinzip der geringsten Privilegien.

Die Knoten in einem Azure Kubernetes-Cluster können wie andere Ressourcen, die mehr in Azure nativ sind, an einem virtuellen Netzwerk teilnehmen. Diese Funktionalität wird als [Azure Container Networking Interface](https://github.com/Azure/azure-container-networking/blob/master/docs/cni.md)bezeichnet. Tatsächlich wird ein Subnetz innerhalb des virtuellen Netzwerks zugewiesen, dem virtuelle Maschinen und Containerabbilder zugeordnet sind.

Wenn Sie den Weg der Veranschaulichung des Prinzips der geringsten Berechtigungen fortsetzen, muss nicht jede Ressource innerhalb eines virtuellen Netzwerks mit jeder anderen Ressource sprechen. In einer Anwendung, die eine Web-API über ein Speicherkonto und eine SQL-Datenbank bereitstellt, ist es beispielsweise unwahrscheinlich, dass die Datenbank und das Speicherkonto miteinander sprechen müssen. Jede gemeinsame Nutzung von Daten zwischen ihnen würde über die Webanwendung gehen. Daher könnte eine [Netzwerksicherheitsgruppe (Network Security Group, NSG)](https://docs.microsoft.com/azure/virtual-network/security-overview) verwendet werden, um den Datenverkehr zwischen den beiden Diensten zu verweigern.

Eine Richtlinie zum Verweigern der Kommunikation zwischen Ressourcen kann bei der Implementierung ärgerlich sein, insbesondere aus dem Hintergrund der Verwendung von Azure ohne Verkehrseinschränkungen. Auf einigen anderen Clouds ist das Konzept der Netzwerksicherheitsgruppen viel häufiger. Die Standardrichtlinie für AWS besteht beispielsweise darin, dass Ressourcen erst dann untereinander kommunizieren können, wenn sie durch Regeln in einer NSG aktiviert sind. Die Entwicklung ist zwar langsamer, aber eine restriktivere Umgebung bietet einen sichereren Standardwert. Die Verwendung geeigneter DevOps-Praktiken, insbesondere die Verwendung von [Azure Resource Manager oder Terraform](infrastructure-as-code.md) zum Verwalten von Berechtigungen, kann die Steuerung der Regeln vereinfachen.

Virtuelle Netzwerke können auch nützlich sein, wenn Sie die Kommunikation zwischen lokalen und Cloud-Ressourcen einrichten. Ein virtuelles privates Netzwerk kann verwendet werden, um die beiden Netzwerke nahtlos miteinander zu verbinden. Dies ermöglicht die Ausführung eines virtuellen Netzwerks ohne jede Art von Gateway für Szenarien, in denen alle Benutzer vor Ort sind. Es gibt eine Reihe von Technologien, die zum Aufbau dieses Netzwerks verwendet werden können. Am einfachsten ist es, ein [Standort-zu-Standort-VPN](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%2fazure%2fvirtual-network%2ftoc.json#s2smulti) zu verwenden, das zwischen vielen Routern und Azure eingerichtet werden kann. Der Datenverkehr wird verschlüsselt und über das Internet zu den gleichen Kosten pro Byte wie jeder andere Datenverkehr getunnelt. Für Szenarien, in denen mehr Bandbreite oder mehr Sicherheit wünschenswert ist, bietet Azure einen Dienst namens [Express Route,](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%2fazure%2fvirtual-network%2ftoc.json#ExpressRoute) der eine private Verbindung zwischen einem lokalen Netzwerk und Azure verwendet. Es ist teurer und schwieriger zu etablieren, aber auch sicherer.

## <a name="role-based-access-control-for-restricting-access-to-azure-resources"></a>Rollenbasierte Zugriffssteuerung zum Einschränken des Zugriffs auf Azure-Ressourcen

RBAC ist ein System, das eine Identität für Anwendungen bereitstellt, die in Azure ausgeführt werden. Anwendungen können auf Ressourcen zugreifen, die diese Identität anstelle oder zusätzlich zur Verwendung von Schlüsseln oder Kennwörtern verwenden.

## <a name="security-principals"></a>Sicherheitsprinzipale

Die erste Komponente in RBAC ist ein Sicherheitsprinzipal. Ein Sicherheitsprinzipal kann ein Benutzer, eine Gruppe, ein Dienstprinzipal oder eine verwaltete Identität sein.

![Abbildung 10-2 Verschiedene Arten](./media/rbac-security-principal.png)
von Sicherheitsprinzipalen**Abbildung 10-2**. Verschiedene Arten von Sicherheitsprinzipalen.

- Benutzer – Jeder Benutzer, der über ein Konto in Azure Active Directory verfügt, ist ein Benutzer.
- Gruppe – Eine Sammlung von Benutzern aus Azure Active Directory. Als Mitglied einer Gruppe übernimmt ein Benutzer zusätzlich zu seiner eigenen Gruppe die Rollen dieser Gruppe.
- Dienstprinzipal – Eine Sicherheitsidentität, unter der Dienste oder Anwendungen ausgeführt werden.
- Verwaltete Identität – Eine Azure Active Directory-Identität, die von Azure verwaltet wird. Verwaltete Identitäten werden in der Regel beim Entwickeln von Cloudanwendungen verwendet, die die Anmeldeinformationen für die Authentifizierung bei Azure-Diensten verwalten.

Der Sicherheitsprinzipal kann auf die meisten Ressourcen angewendet werden. Dies bedeutet, dass es möglich ist, einem Container, der in Azure Kubernetes ausgeführt wird, einen Sicherheitsprinzipal zuzuweisen, sodass er auf in Key Vault gespeicherte Geheimnisse zugreifen kann. Eine Azure-Funktion kann eine Berechtigung annehmen, die es ihr ermöglicht, mit einer Active Directory-Instanz zu sprechen, um ein JWT für einen aufrufenden Benutzer zu überprüfen. Sobald Dienste mit einem Dienstprinzipal aktiviert sind, können ihre Berechtigungen mithilfe von Rollen und Bereichen granular verwaltet werden.

## <a name="roles"></a>Rollen

Ein Sicherheitsprinzipal kann viele Rollen übernehmen oder mit einer sartorialeren Analogie viele Hüte tragen. Jede Rolle definiert eine Reihe von Berechtigungen, z. B. "Nachrichten vom Azure Service Bus-Endpunkt lesen". Der effektive Berechtigungssatz eines Sicherheitsprinzipals ist die Kombination aller Berechtigungen, die allen Rollen zugewiesen sind, über die der Sicherheitsprinzipal verfügt. Azure verfügt über eine große Anzahl integrierter Rollen, und Benutzer können ihre eigenen Rollen definieren.

![Abbildung 10-3 RBAC-Rollendefinitionen](./media/rbac-role-definition.png)
Abbildung**10-3**. RBAC-Rollendefinitionen.

In Azure sind auch eine Reihe von übergeordneten Rollen wie Besitzer, Mitwirkender, Leser und Benutzerkontoadministrator integriert. Mit der Rolle "Besitzer" kann ein Sicherheitsprinzipal auf alle Ressourcen zugreifen und anderen Berechtigungen zuweisen. Ein Mitwirkender hat die gleiche Zugriffsebene auf alle Ressourcen, kann jedoch keine Berechtigungen zuweisen. Ein Reader kann nur vorhandene Azure-Ressourcen anzeigen, und ein Benutzerkontoadministrator kann den Zugriff auf Azure-Ressourcen verwalten.

Detailliertere integrierte Rollen wie [DNS Zone Contributor](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles#dns-zone-contributor) verfügen über Rechte, die auf einen einzelnen Dienst beschränkt sind. Sicherheitsprinzipale können eine beliebige Anzahl von Rollen übernehmen.

## <a name="scopes"></a>Bereiche

Rollen können auf einen eingeschränkten Satz von Ressourcen in Azure angewendet werden. Wenn Sie z. B. den Bereich auf das vorherige Beispiel zum Lesen aus einer Service Bus-Warteschlange `blah.servicebus.windows.net/queue1`anwenden, können Sie die Berechtigung auf eine einzelne Warteschlange beschränken: "Nachrichten vom Azure Service Bus-Endpunkt lesen "

Der Bereich kann so schmal sein wie eine einzelne Ressource oder kann auf eine gesamte Ressourcengruppe, ein Abonnement oder sogar eine Verwaltungsgruppe angewendet werden.

Beim Testen, ob ein Sicherheitsprinzipal über eine bestimmte Berechtigung verfügt, wird die Kombination von Rolle und Umfang berücksichtigt. Diese Kombination bietet einen leistungsstarken Autorisierungsmechanismus.

## <a name="deny"></a>Verweigern

Bisher waren nur "Zulassen"-Regeln für RBAC zulässig. Dieses Verhalten erschwerte die Erstellung einiger Bereiche. Beispielsweise kann ein Sicherheitsprinzipal Zugriff auf alle Speicherkonten gewähren, mit Ausnahme eines erforderlichen Zugriffs auf eine potenziell endlose Liste von Speicherkonten. Jedes Mal, wenn ein neues Speicherkonto erstellt wird, muss es dieser Kontenliste hinzugefügt werden. Dies zusätzliche Management-Overhead, die sicherlich nicht wünschenswert war.

Verweigern von Regeln hat Vorrang vor Zulassungsregeln. Nun könnte der gleiche Bereich "Alle außer einem zulassen" als zwei Regeln "alle zulassen" und "diese eine bestimmte" "verweigern" dargestellt werden. Verweigern von Regeln erleichtert nicht nur die Verwaltung, sondern ermöglicht auch Ressourcen, die besonders sicher sind, indem sie allen den Zugriff verweigern.

## <a name="checking-access"></a>Überprüfen des Zugriffs

Wie Sie sich vorstellen können, kann es mit einer großen Anzahl von Rollen und Bereichen schwierig sein, die effektive Berechtigung eines Dienstprinzipals herauszuarbeiten. Piling leugnet obendrein Regeln, dient nur dazu, die Komplexität zu erhöhen. Glücklicherweise gibt es einen Berechtigungsrechner, der die effektiven Berechtigungen für jeden Dienstprinzipal anzeigen kann. Sie befindet sich in der Regel unter der Registerkarte IAM im Portal, wie in Abbildung 10-3 dargestellt.

![Abbildung 10-4 Berechtigungsrechner](./media/check-rbac.png)
für einen**App-Dienst Abbildung 10-4**. Berechtigungsrechner für einen App-Dienst.

## <a name="securing-secrets"></a>Sichern von Geheimnissen

Kennwörter und Zertifikate sind ein gängiger Angriffsvektor für Angreifer. Kennwort-Cracking-Hardware kann einen Brute-Force-Angriff begehen und versuchen, Milliarden von Passwörtern pro Sekunde zu erraten. Daher ist es wichtig, dass die Kennwörter, die für den Zugriff auf Ressourcen verwendet werden, stark sind, mit einer Vielzahl von Zeichen. Diese Kennwörter sind genau die Art von Kennwörtern, die fast unmöglich zu merken sind. Glücklicherweise müssen die Kennwörter in Azure eigentlich keinem Menschen bekannt sein.

Viele [Sicherheitsexperten schlagen vor,](https://www.troyhunt.com/password-managers-dont-have-to-be-perfect-they-just-have-to-be-better-than-not-having-one/) dass die Verwendung eines Passwort-Managers, um Ihre eigenen Passwörter zu behalten, der beste Ansatz ist. Während es Ihre Kennwörter an einem Ort zentralisiert, ermöglicht es auch die Verwendung hochkomplexer Kennwörter und stellt sicher, dass sie für jedes Konto eindeutig sind. Das gleiche System existiert in Azure: ein zentraler Speicher für Geheimnisse.

## <a name="azure-key-vault"></a>Azure-Schlüsseltresor

Azure Key Vault bietet einen zentralen Speicherort zum Speichern von Kennwörtern für Z. B. Datenbanken, API-Schlüssel und Zertifikate. Sobald ein Geheimnis in den Tresor eingegeben wurde, wird es nie wieder angezeigt und die Befehle zum Extrahieren und Anzeigen sind absichtlich kompliziert. Die Informationen im Safe werden entweder durch Softwareverschlüsselung oder FIPS 140-2 Level 2 validierte Hardware-Sicherheitsmodule geschützt.

Der Zugriff auf den Schlüsseltresor erfolgt über RBACs, was bedeutet, dass nicht nur jeder Benutzer auf die Informationen im Tresor zugreifen kann. Angenommen, eine Webanwendung möchte auf die in Azure Key Vault gespeicherte Datenbankverbindungszeichenfolge zugreifen. Um Zugriff zu erhalten, müssen Anwendungen mit einem Dienstprinzipal ausgeführt werden. Unter dieser übernommenen Rolle können sie die Geheimnisse aus dem Tresor lesen. Es gibt eine Reihe von verschiedenen Sicherheitseinstellungen, die den Zugriff einer Anwendung auf den Tresor weiter einschränken können, sodass sie keine Geheimnisse aktualisieren, sondern nur lesen kann.

Der Zugriff auf den Schlüsseltresor kann überwacht werden, um sicherzustellen, dass nur die erwarteten Anwendungen auf den Tresor zugreifen. Die Protokolle können wieder in Azure Monitor integriert werden, wodurch Warnungen eingerichtet werden können, wenn unerwartete Bedingungen auftreten.

## <a name="kubernetes"></a>Kubernetes

Innerhalb von Kubernetes gibt es einen ähnlichen Service für die Pflege kleiner geheimer Informationen. Kubernetes Secrets kann über `kubectl` die typische ausführbare Datei eingestellt werden.

Das Erstellen eines Geheimen ist so einfach wie das Suchen der base64-Version der zu speichernden Werte:

```console
echo -n 'admin' | base64
YWRtaW4=
echo -n '1f2d1e2e67df' | base64
MWYyZDFlMmU2N2Rm
```

Fügen Sie sie dann `secret.yml` einer geheimen Datei mit dem Namen hinzu, die dem folgenden Beispiel ähnelt:

```yml
apiVersion: v1
kind: Secret
metadata:
  name: mysecret
type: Opaque
data:
  username: YWRtaW4=
  password: MWYyZDFlMmU2N2Rm
```

Schließlich kann diese Datei in Kubernetes geladen werden, indem Sie den folgenden Befehl ausführen:

```console
kubectl apply -f ./secret.yaml
```

Diese Geheimnisse können dann in Volumes eingehängt oder über Umgebungsvariablen Containerprozessen ausgesetzt werden. Der [Zwölf-Faktor-App-Ansatz](https://12factor.net/) zum Erstellen von Anwendungen schlägt vor, den kleinsten gemeinsamen Nenner zu verwenden, um Einstellungen an eine Anwendung zu übertragen. Umgebungsvariablen sind der kleinste gemeinsame Nenner, da sie unabhängig vom Betriebssystem oder der Anwendung unterstützt werden.

Eine Alternative zur Verwendung der integrierten Kubernetes-Geheimnisse besteht darin, von Kubernetes aus auf die Geheimnisse in Azure Key Vault zuzugreifen. Die einfachste Möglichkeit besteht darin, dem Container eine RBAC-Rolle zuzuweisen, die Geheimnisse laden möchte. Die Anwendung kann dann die Azure Key Vault-APIs verwenden, um auf die Geheimnisse zuzugreifen. Dieser Ansatz erfordert jedoch Änderungen am Code und folgt nicht dem Muster der Verwendung von Umgebungsvariablen. Stattdessen ist es möglich, Werte mithilfe des Azure [Key Vault Injektors](https://mrdevops.io/introducing-azure-key-vault-to-kubernetes-931f82364354)in einen Container einzuschleusen. Dieser Ansatz ist tatsächlich sicherer als die Verwendung der Kubernetes-Geheimnisse direkt, da Benutzer im Cluster darauf zugreifen können.

## <a name="encryption-in-transit-and-at-rest"></a>Verschlüsselung während der Übertragung und im Ruhezustand

Die Sicherheit der Daten ist wichtig, egal ob auf der Festplatte oder beim Transit zwischen verschiedenen Diensten. Der effektivste Weg, um Daten vor Dementaucharbeiten zu bewahren, besteht darin, sie in ein Format zu verschlüsseln, das von anderen nicht leicht gelesen werden kann. Azure unterstützt eine Vielzahl von Verschlüsselungsoptionen.

### <a name="in-transit"></a>Während der Übertragung

Es gibt mehrere Möglichkeiten, den Datenverkehr im Netzwerk in Azure zu verschlüsseln. Der Zugriff auf Azure-Dienste erfolgt in der Regel über Verbindungen, die Transport Layer Security (TLS) verwenden. Beispielsweise erfordern alle Verbindungen zu den Azure-APIs TLS-Verbindungen. Ebenso können Verbindungen zu Endpunkten im Azure-Speicher auf die Arbeit nur über TLS-verschlüsselte Verbindungen beschränkt werden.

TLS ist ein kompliziertes Protokoll und einfach zu wissen, dass die Verbindung TLS verwendet, reicht nicht aus, um die Sicherheit zu gewährleisten. Zum Beispiel ist TLS 1.0 chronisch unsicher, und TLS 1.1 ist nicht viel besser. Selbst innerhalb der Versionen von TLS gibt es verschiedene Einstellungen, die die Verbindung einfacher zu entschlüsseln machen können. Am besten prüfen sie, ob die Serververbindung aktuelle und gut konfigurierte Protokolle verwendet.

Diese Prüfung kann von einem externen Dienst wie SSL Labs SSL-Servertest durchgeführt werden. Ein Testlauf gegen einen typischen Azure-Endpunkt, in diesem Fall ein Dienstbusendpunkt, ergibt eine nahezu perfekte Punktzahl von A.

Selbst Dienste wie Azure SQL-Datenbanken verwenden TLS-Verschlüsselung, um Daten ausgeblendet zu halten. Der interessante Teil über die Verschlüsselung der Daten während der Übertragung mit TLS ist, dass es nicht möglich ist, auch für Microsoft, auf die Verbindung zwischen Computern mit TLS zu hören. Dies sollte Unternehmen, die betroffen sind, Trost spenden, dass ihre Daten von Microsoft selbst oder sogar einem staatlichen Akteur mit mehr Ressourcen als dem Standardangreifer gefährdet sein könnten.

![Abbildung 10-5 SSL-Labors-Bericht mit der Punktzahl A für einen Service Bus-Endpunkt. ](./media/ssl-report.png)
 **Abbildung 10-5**. SSL-Laborberichte mit der Punktzahl A für einen Service Bus-Endpunkt.

Obwohl diese Verschlüsselungsstufe nicht für alle Zeiten ausreicht, sollte sie die Zuversicht wecken, dass Azure TLS-Verbindungen ziemlich sicher sind. Azure wird seine Sicherheitsstandards weiterentwickeln, wenn die Verschlüsselung verbessert wird. Es ist schön zu wissen, dass es jemanden gibt, der die Sicherheitsstandards beobachtet und Azure aktualisiert, während sie sich verbessern.

### <a name="at-rest"></a>Im Ruhezustand

In jeder Anwendung gibt es eine Reihe von Stellen, an denen Daten auf dem Datenträger gespeichert sind. Der Anwendungscode selbst wird von einem Speichermechanismus geladen. Die meisten Anwendungen verwenden auch eine Art von Datenbank wie SQL Server, Cosmos DB oder sogar den erstaunlich preiseffizienten Tabellenspeicher. Diese Datenbanken verwenden alle stark verschlüsselten Speicher, um sicherzustellen, dass niemand anderes als die Anwendungen mit den entsprechenden Berechtigungen Ihre Daten lesen kann. Selbst die Systembetreiber können verschlüsselte Daten nicht lesen. So können Kunden sicher bleiben, dass ihre geheimen Informationen geheim bleiben.

### <a name="storage"></a>Storage

Die Grundlage eines Großteils von Azure ist das Azure Storage-Modul. Festplatten virtueller Computer werden über Azure Storage bereitgestellt. Azure Kubernetes Services werden auf virtuellen Computern ausgeführt, die selbst in Azure Storage gehostet werden. Selbst serverlose Technologien, wie Azure Functions Apps und Azure Container Instances, verfügen nicht mehr über den Datenträger, der Teil von Azure Storage ist.

Wenn Azure Storage gut verschlüsselt ist, bietet es eine Grundlage für die meisten anderen, um auch verschlüsselt zu werden. Azure Storage ist mit [FIPS 140-2-kompatiblem](https://en.wikipedia.org/wiki/FIPS_140) [256-Bit-AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) [verschlüsselt.](https://docs.microsoft.com/azure/storage/common/storage-service-encryption) Dies ist eine angesehene Verschlüsselungstechnologie, die in den letzten 20 Jahren einer umfassenden wissenschaftlichen Prüfung unterzogen wurde. Derzeit gibt es keinen bekannten praktischen Angriff, der es jemandem ohne Kenntnis des Schlüssels ermöglichen würde, von AES verschlüsselte Daten zu lesen.

Standardmäßig werden die Schlüssel, die zum Verschlüsseln von Azure Storage verwendet werden, von Microsoft verwaltet. Es gibt umfangreiche Schutzmaßnahmen, um böswilligen Zugriff auf diese Schlüssel zu verhindern. Benutzer mit bestimmten Verschlüsselungsanforderungen können jedoch auch [eigene Speicherschlüssel bereitstellen,](https://docs.microsoft.com/azure/storage/common/storage-encryption-keys-powershell) die in Azure Key Vault verwaltet werden. Diese Schlüssel können jederzeit widerrufen werden, wodurch der Inhalt des Speicherkontos, das sie verwendet, effektiv nicht mehr zugänglich wäre.

Virtuelle Maschinen verwenden verschlüsselten Speicher, aber es ist möglich, eine weitere Verschlüsselungsebene bereitzustellen, indem Technologien wie BitLocker unter Windows oder DM-Crypt unter Linux verwendet werden. Diese Technologien bedeuten, dass selbst wenn das Festplattenabbild aus dem Speicher ausgetreten wäre, es nahezu unmöglich wäre, es zu lesen.

### <a name="azure-sql"></a>Azure SQL

In Azure SQL gehostete Datenbanken verwenden eine Technologie namens [Transparente Datenverschlüsselung (Transparent Data Encryption, TDE),](/sql/relational-databases/security/encryption/transparent-data-encryption) um sicherzustellen, dass Daten verschlüsselt bleiben. Sie ist standardmäßig für alle neu erstellten SQL-Datenbanken aktiviert, muss jedoch manuell für ältere Datenbanken aktiviert werden. TDE führt die Echtzeitverschlüsselung und -entschlüsselung nicht nur der Datenbank, sondern auch der Backups und Transaktionsprotokolle durch.

Die Verschlüsselungsparameter werden `master` in der Datenbank gespeichert und beim Start für die verbleibenden Vorgänge in den Arbeitsspeicher eingelesen. Dies bedeutet, dass die `master` Datenbank unverschlüsselt bleiben muss. Der tatsächliche Schlüssel wird von Microsoft verwaltet. Benutzer mit hohen Sicherheitsanforderungen können jedoch ihren eigenen Schlüssel in Key Vault auf die gleiche Weise bereitstellen, wie dies bei Azure Storage der Vorgesehen ist. Der Schlüsseltresor bietet Dienste wie Schlüsselrotation und Widerruf.

Der "Transparente" Teil von TDS stammt aus der Tatsache, dass keine Clientänderungen erforderlich sind, um eine verschlüsselte Datenbank zu verwenden. Obwohl dieser Ansatz für eine gute Sicherheit sorgt, reicht das Durchsickern des Datenbankkennworts aus, damit Benutzer die Daten entschlüsseln können. Es gibt einen anderen Ansatz, der einzelne Spalten oder Tabellen in einer Datenbank verschlüsselt. [Always Encrypted](https://docs.microsoft.com/azure/sql-database/sql-database-always-encrypted-azure-key-vault) stellt sicher, dass die verschlüsselten Daten zu keinem Zeitpunkt im Klartext in der Datenbank angezeigt werden.

Das Einrichten dieser Verschlüsselungsstufe erfordert die Ausführung über einen Assistenten in SQL Server Management Studio, um die Art der Verschlüsselung auszuwählen und wo in Key Vault die zugehörigen Schlüssel gespeichert werden sollen.

![Abbildung 10-6 Auswählen von Spalten in einer Tabelle, die mit Always Encrypted](./media/always-encrypted.png)
Abbildung**10-6**verschlüsselt werden soll. Auswählen von Spalten in einer Tabelle, die mit Always Encrypted verschlüsselt werden sollen.

Clientanwendungen, die Informationen aus diesen verschlüsselten Spalten lesen, müssen dem Lesen verschlüsselter Daten besondere Zulagen einteilen. Verbindungszeichenfolgen müssen mit `Column Encryption Setting=Enabled` aktualisiert werden, und Clientanmeldeinformationen müssen aus dem Schlüsseltresor abgerufen werden. Der SQL Server-Client muss dann mit den Spaltenverschlüsselungsschlüsseln grundiert werden. Sobald dies geschehen ist, verwenden die verbleibenden Aktionen die Standardschnittstellen zu SQL Client. Das heißt, Tools wie Dapper und Entity Framework, die auf SQL Client basieren, werden weiterhin ohne Änderungen funktionieren. Always Encrypted ist möglicherweise noch nicht für jeden SQL Server-Treiber in jeder Sprache verfügbar.

Die Kombination von TDE und Always Encrypted, die beide mit clientspezifischen Schlüsseln verwendet werden können, stellt sicher, dass selbst die anspruchsvollsten Verschlüsselungsanforderungen unterstützt werden.

### <a name="cosmos-db"></a>Cosmos DB

Cosmos DB ist die neueste Datenbank, die von Microsoft in Azure bereitgestellt wird. Es wurde von Grund auf mit Sicherheit und Kryptographie im Hinterkopf gebaut. Die AES-256bit-Verschlüsselung ist Standard für alle Cosmos DB-Datenbanken und kann nicht deaktiviert werden. In Verbindung mit der TLS 1.2-Anforderung für die Kommunikation wird die gesamte Speicherlösung verschlüsselt.

![Abbildung 10-7 Der Fluss der Datenverschlüsselung innerhalb von Cosmos DB](./media/cosmos-encryption.png)
Abbildung**10-7**. Der Fluss der Datenverschlüsselung innerhalb von Cosmos DB.

Cosmos DB bietet zwar keine Kundenverschlüsselungsschlüssel an, aber das Team hat erhebliche Arbeit geleistet, um sicherzustellen, dass es PCI-DSS-kompatibel bleibt, ohne dies nicht zu tun. Cosmos DB unterstützt auch keine Einzelnespaltenverschlüsselung, die Der Azure SQL-Verschlüsselung s.

## <a name="keeping-secure"></a>Sicherheit

Azure verfügt über alle Tools, die zum Veröffentlichen eines hochsicheren Produkts erforderlich sind. Eine Kette ist jedoch nur so stark wie ihr schwächstes Glied. Wenn die zusätzlich zu Azure bereitgestellten Anwendungen nicht mit einer angemessenen Sicherheitseinstellung und guten Sicherheitsüberwachungen entwickelt werden, werden sie zum schwachen Glied in der Kette. Es gibt viele großartige statische Analysetools, Verschlüsselungsbibliotheken und Sicherheitspraktiken, die verwendet werden können, um sicherzustellen, dass die in Azure installierte Software so sicher ist wie Azure selbst. Beispiele hierfür sind [statische Analysetools](https://www.whitesourcesoftware.com/), [Verschlüsselungsbibliotheken](https://www.libressl.org/)und [Sicherheitspraktiken](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/).

>[!div class="step-by-step"]
>[Zurück](security.md)
>[Weiter](devops.md)
