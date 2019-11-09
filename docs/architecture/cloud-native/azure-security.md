---
title: Azure-Sicherheit für Native Cloud-apps
description: Architektur von Cloud Native .net-apps für Azure | Azure-Sicherheit für Native Cloud-apps
ms.date: 06/30/2019
ms.openlocfilehash: 44e81bc91fa952448f501a29e9db8afb2dbda752
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "73841270"
---
# <a name="azure-security-for-cloud-native-apps"></a>Azure-Sicherheit für Native Cloud-apps

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Native Cloud-Anwendungen können einfacher und schwieriger zu schützen als herkömmliche Anwendungen. Der Nachteil ist, dass Sie kleinere Anwendungen sichern und mehr Energie aufwenden müssen, um die Sicherheitsinfrastruktur zu erstellen. Die heterogene Natur der Programmiersprachen und Stile in den meisten Dienst Bereitstellungen bedeutet auch, dass Sie die Sicherheits Bulletins von vielen unterschiedlichen Anbietern berücksichtigen müssen.

Auf der Flip-Seite beschränken kleinere Dienste, die jeweils über einen eigenen Datenspeicher verfügen, den Umfang eines Angriffs. Wenn ein Angreifer ein System kompromittiert, ist es für den Angreifer wahrscheinlich schwieriger, den Sprung zu einem anderen System als in einer monolithischen Anwendung zu machen. Prozess Grenzen sind starke Grenzen. Außerdem ist die Beschädigung, wenn eine Datenbanksicherung nicht vorhanden ist, stärker eingeschränkt, da diese Datenbank nur eine Teilmenge der Daten enthält und wahrscheinlich keine personenbezogenen Daten enthält.

## <a name="threat-modeling"></a>Bedrohungsmodellierung

Unabhängig davon, ob die Vorteile die Nachteile von cloudbasierten Anwendungen überwiegen, muss dieselbe ganzheitliche Sicherheits Denkweise befolgt werden. Sicherheit und sicheres denken müssen Teil jedes Schritts der Entwicklungs-und Betriebsgeschichte sein. Wenn Sie eine Anwendung planen, stellen Sie Fragen wie:

- Welche Auswirkungen haben diese Daten verloren?
- Wie können wir den Schaden von ungültigen Daten, die in diesen Dienst eingefügt werden, einschränken?
- Wer sollte Zugriff auf diese Daten haben?
- Gibt es Überwachungs Richtlinien für den Entwicklungs-und Releaseprozess?

Alle diese Fragen sind Teil eines Prozesses namens [Bedrohungsmodellierung](https://docs.microsoft.com/azure/security/azure-security-threat-modeling-tool). Bei diesem Prozess wird versucht, die Frage zu beantworten, welche Bedrohungen für das System bestehen, wie wahrscheinlich die Bedrohungen sind und welche potenzielle Schäden daraus bestehen.

Nachdem die Liste der Bedrohungen festgelegt wurde, müssen Sie entscheiden, ob Sie eine Minderung durchführen möchten. Manchmal ist eine Bedrohung so unwahrscheinlich und teuer, dass es nicht sinnvoll ist, Energie zu investieren. Beispielsweise könnte ein Actor auf Zustands Ebene Änderungen in den Entwurf eines Prozesses einfügen, der von Millionen von Geräten verwendet wird. Anstatt ein bestimmtes Code Element in [Ring 3](https://en.wikipedia.org/wiki/Protection_ring)auszuführen, wird dieser Code in Ring 0 ausgeführt. Dies ermöglicht eine Ausnutzung, mit der der Hypervisor umgangen und der Angriffs Code auf den Bare-Metal-Computern ausgeführt werden kann. Dies ermöglicht Angriffe auf alle virtuellen Maschinen, die auf der Hardware ausgeführt werden.

Die geänderten Prozessoren sind schwer zu erkennen, ohne dass ein Mikroskop und erweiterte Kenntnisse des auf dem Silicon Design dieses Prozessors vorliegen. Dieses Szenario ist unwahrscheinlich und kostenaufwendig zu beheben. wahrscheinlich empfiehlt es sich nicht, ein Bedrohungs Modell dafür zu entwickeln.

Wahrscheinlichere Bedrohungen, wie z. b. unterbrochene Zugriffs Steuerungen, die `Id` inkrementellen Angriffen zulassen (Ersetzen von `Id=2` durch `Id=3` in der URL) oder SQL Injection, sind attraktiver, um Schutzmaßnahmen zu bieten. Die entschärfungen für diese Bedrohungen sind recht vernünftig, um peinliche Sicherheitslücken zu erstellen und zu verhindern, die den Ruf des Unternehmens unterscheiden.

## <a name="principle-of-least-privilege"></a>Prinzip der geringsten Berechtigung

Eine der Gründer Ideen bei der Computersicherheit ist das Prinzip der geringsten Rechte (POLP). Es ist eine grundlegende Idee in den meisten Formen der Sicherheit, dass Sie Digital oder physisch ist. Kurz gesagt, das Prinzip ist, dass jeder Benutzer oder Prozess über die kleinste Anzahl von Rechten verfügen sollte, um seine Aufgabe ausführen zu können.

Stellen Sie sich als Beispiel den Kassierer an einer Bank vor: der Zugriff auf den Safe ist eine ungewöhnliche Aktivität. Daher kann der durchschnittliche Kassierer den sicheren selbst nicht öffnen. Um Zugriff zu erhalten, müssen Sie Ihre Anforderung über einen Bankmanager eskalieren, der zusätzliche Sicherheitsüberprüfungen ausführt.

In einem Computersystem ist ein fantastisches Beispiel die Rechte eines Benutzers, der eine Verbindung mit einer Datenbank herstellt. In vielen Fällen gibt es ein einzelnes Benutzerkonto, das verwendet wird, um die Datenbankstruktur zu erstellen und die Anwendung auszuführen. Das Konto, auf dem die Anwendung ausgeführt wird, benötigt nicht die Möglichkeit, Schema Informationen zu aktualisieren. Es sollten mehrere Konten vorhanden sein, die unterschiedliche Berechtigungsstufen bieten. Die Anwendung sollte nur die Berechtigungsstufe verwenden, die Lese-und Schreibzugriff auf die Daten in den Tabellen gewährt. Durch diese Art von Schutz werden Angriffe vermieden, die Datenbanktabellen löschen oder schädliche Trigger auslösen.

Fast jeder Teil der Bildung einer Cloud-native Anwendung kann von der Erinnerung an das Prinzip der geringsten Rechte profitieren. Sie finden es beim Einrichten von Firewalls, Netzwerk Sicherheitsgruppen, Rollen und Bereichen in der rollenbasierten Zugriffs Steuerung (Role-Based Access Control, RBAC).

## <a name="penetration-testing"></a>Penetrationstests

Wenn Anwendungen komplizierter werden, erhöht sich die Anzahl der Angriffsvektoren mit alarmierender Geschwindigkeit. Die Bedrohungsmodellierung ist insofern fehlerhaft, als Sie in der Regel von denselben Personen ausgeführt wird, die das System aufbauen. Ebenso wie viele Entwickler Probleme bei der Entwicklung von Benutzerinteraktionen und der anschließenden Erstellung nicht verwendbarer Benutzeroberflächen haben, haben die meisten Entwickler Schwierigkeiten, jeden Angriffsvektor zu sehen. Es ist auch möglich, dass sich die Entwickler, die das System aufbauen, nicht gut mit Angriffsmethoden auskennen und etwas Wichtiges übersehen.

Penetrationstests oder "Stift Tests" beinhalten die Einbindung externer Actors, um Angriffe auf das System durchzuführen. Dabei kann es sich um ein externes Beratungsunternehmen oder um andere Entwickler mit guten Sicherheits Kenntnissen aus einem anderen Teil des Unternehmens handeln. Sie erhalten eine Hand Hand, um zu versuchen, das System zu unterteilen. Häufig finden Sie umfassende Sicherheitslücken, die gepatcht werden müssen. Manchmal ist der Angriffsvektor etwas unerwartetes wie das Ausnutzen eines Phishingangriffen gegen den CEO.

Azure selbst hat immer wieder Angriffe von einem [Team von Hacker innerhalb von Microsoft](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/). Im Laufe der Jahre war es der erste, Dutzende potenziell schwerwiegender Angriffsvektoren zu finden und diese zu schließen, bevor Sie extern ausgenutzt werden können. Umso wahrscheinlicher ist es, dass ewig Actors versuchen, das Ziel auszunutzen, und es gibt ein paar Ziele auf der Welt, die eher verlockend sind als Azure.

## <a name="monitoring"></a>Überwachung

Wenn ein Angreifer versucht, eine Anwendung zu durchdringen, sollte eine Warnung vorliegen. Häufig können Angriffe durch Untersuchen der Protokolle von Diensten erkannt werden. Angriffe hinterlassen klarer Zeichen, die vor dem Erfolg erkannt werden können. Beispielsweise nimmt ein Angreifer, der versucht, ein Kennwort zu erraten, viele Anforderungen an ein Anmeldesystem an. Durch die Überwachung des Anmeldesystems können seltsame Muster erkannt werden, die mit dem typischen Zugriffsmuster nicht übereinstimmen. Diese Überwachung kann in eine Warnung umgewandelt werden, die wiederum einen Vorgangs Mitarbeiter warnen kann, um eine bestimmte Art von Gegenmaßnahme zu aktivieren. Ein stark ausgereiftes Überwachungssystem kann sogar auf der Grundlage dieser Abweichungen Maßnahmen ergreifen, die proaktiv Regeln zum Blockieren von Anforderungen oder Einschränken von Antworten hinzufügen.

## <a name="securing-the-build"></a>Sichern des Builds

Ein Ort, an dem Sicherheit oft übersehen wird, ist um den Buildprozess herum. Der Build sollte nicht nur Sicherheitsüberprüfungen ausführen, wie z. b. das Überprüfen auf unsicheren Code oder eingecheckte Anmelde Informationen, sondern der Build selbst muss sicher sein. Wenn der Buildserver kompromittiert ist, bietet er einen fantastischen Vektor für die Einführung von beliebigem Code in das Produkt.

Stellen Sie sich vor, dass ein Angreifer die Kenn Wörter von Personen stehlen möchte, die sich bei einer Webanwendung anmelden. Sie könnten einen Buildschritt einführen, der den ausgecheckten Code so ändert, dass er beliebige Anmelde Anforderungen an einen anderen Server widerspiegelt. Der nächste Zeitpunkt, zu dem der Code den Build durchläuft, wird automatisch aktualisiert. Die Überprüfung der Quell Code Anfälligkeit fängt diese nicht ab, wenn Sie vor dem Build ausgeführt wird. Ebenso fängt niemand Sie in einem Code Review ab, da die Buildschritte auf dem Buildserver ausgeführt werden. Der ausgebeutete Code wird in die Produktion geleitet, wo er Kenn Wörter ernten kann. Es ist wahrscheinlich kein Überwachungs Protokoll des buildprozessprozesses vorhanden oder zumindest niemand, der die Überwachung überwacht.

Dies ist ein perfektes Beispiel für ein scheinbar niedriges Ziel, das zum Unterbrechen des Systems verwendet werden kann. Nachdem ein Angreifer den Umkreis des Systems verletzt hat, kann er mit der Suche nach Möglichkeiten zum herauf Stufen der Berechtigungen auf den Punkt beginnen, an dem Sie jederzeit echte Schäden verursachen können.

## <a name="building-secure-code"></a>Aufbauen von sicherem Code

Der .NET Framework ist bereits ein sehr sicheres Framework. Dabei werden einige der Fehler von nicht verwaltetem Code vermieden, z. b. das Durchlaufen der Enden von Arrays. Die Arbeit wird aktiv durchgeführt, um Sicherheitslücken zu beheben, wenn Sie erkannt werden. Es gibt sogar ein [Programm zur Fehler](https://www.microsoft.com/msrc/bounty) Behebung, mit dem Forscher Probleme im Framework finden und Sie melden, anstatt sie auszunutzen.

Es gibt viele Möglichkeiten, .NET-Code sicherer zu machen. Die folgenden Richtlinien, wie z. b. die [Richtlinien für die sichere Codierung für .net](https://docs.microsoft.com/dotnet/standard/security/secure-coding-guidelines) , sind ein angemessener Schritt, um sicherzustellen, dass der Code von Grund auf sicher ist. Der [OWASP Top 10](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_2017_Project) ist ein weiterer unschätzbarer Leitfaden zum Erstellen von sicherem Code.

Der Buildprozess ist ein guter Ausgangspunkt, um Scan Tools zu platzieren, um Probleme im Quellcode zu erkennen, bevor Sie Sie in die Produktion versetzen. Die meisten Projekte weisen Abhängigkeiten von einigen anderen Paketen auf. Ein Tool, das nach veralteten Paketen suchen kann, fängt Probleme in einem nächtlichen Build ab. Selbst beim Erstellen von Docker-Images ist es sinnvoll, zu überprüfen und sicherzustellen, dass das Basis Image keine bekannten Sicherheitsrisiken aufweist. Ein weiterer zu überprüfende Punkt ist, dass niemand versehentlich Anmelde Informationen eingecheckt hat.

## <a name="built-in-security"></a>Integrierte Sicherheit

Azure ist so konzipiert, dass die Benutzerfreundlichkeit und Sicherheit für die meisten Benutzer ausgeglichen werden. Unterschiedliche Benutzer haben unterschiedliche Sicherheitsanforderungen, sodass Sie Ihren Ansatz für die cloudsicherheit optimieren müssen. Microsoft veröffentlicht viele Sicherheitsinformationen im [Trust Center](https://azure.microsoft.com/support/trust-center/). Diese Ressource sollte der erste Anlaufpunkt für diese Fachleute sein, um zu verstehen, wie die integrierten Angriffe zur Abwehr von Angriffen funktionieren.

Innerhalb des Azure-Portal ist die [Azure Advisor](https://azure.microsoft.com/services/advisor/) ein System, das ständig eine Umgebung scannt und Empfehlungen sendet. Einige dieser Empfehlungen sind so konzipiert, dass Benutzer Geld sparen können, aber andere sind darauf ausgelegt, potenziell unsichere Konfigurationen zu erkennen, z. b. einen Speicher Container, der auf der ganzen Welt offen ist und nicht durch eine Virtual Network geschützt wird.

## <a name="azure-network-infrastructure"></a>Azure-Netzwerkinfrastruktur

In einer lokalen Bereitstellungs Umgebung ist eine große Menge an Energie für das Einrichten von Netzwerken vorgesehen. Das Einrichten von Routern, Switches und dem solchen ist eine komplizierte Arbeit. Mit Netzwerken können bestimmte Ressourcen mit anderen Ressourcen kommunizieren und in einigen Fällen den Zugriff verhindern. Eine häufige Netzwerk Regel besteht darin, den Zugriff auf die Produktionsumgebung von der Entwicklungsumgebung aus zu deaktivieren, wenn ein Teil des Codes mit einem Teil des Codes eintreten ausführt und einen Daten Satz löscht.

Standardmäßig verfügen die meisten Azure-Ressourcen in Azure nur über die grundlegende und leistungsbezogene Netzwerk Einrichtung. Beispielsweise kann jeder im Internet auf einen app Service zugreifen. Neue SQL Server Instanzen sind in der Regel eingeschränkt, sodass externe Parteien nicht darauf zugreifen können, aber die von Azure selbst verwendeten IP-Adressbereiche sind über zulässig. Obwohl der SQL-Server vor externen Bedrohungen geschützt ist, muss ein Angreifer nur einen Azure-Bridgeheadserver einrichten, von dem aus Angriffe auf alle SQL-Instanzen in Azure gestartet werden können.

Glücklicherweise können die meisten Azure-Ressourcen in einer Azure-Virtual Network platziert werden, die eine präzisere Zugriffs Steuerung ermöglicht. Ähnlich der Art und Weise, wie lokale Netzwerke private Netzwerke einrichten, die vor der umfassenderen Welt geschützt sind, sind virtuelle Netzwerke Inseln mit privaten IP-Adressen, die sich innerhalb des Azure-Netzwerks befinden.

![Abbildung 10-1 ein virtuelles Netzwerk in Azure](./media/virtual-network.png)
**Abbildung 10-1**. Ein virtuelles Netzwerk in Azure.

Auf die gleiche Weise, wie lokale Netzwerke über eine Firewall verfügen, die den Zugriff auf das Netzwerk regelt, können Sie eine ähnliche Firewall an der Grenze des virtuellen Netzwerks einrichten. Standardmäßig können alle Ressourcen in einem virtuellen Netzwerk weiterhin mit dem Internet kommunizieren. Es handelt sich nur um eingehende Verbindungen, für die eine explizite Firewallausnahme erforderlich ist.

Wenn das Netzwerk eingerichtet ist, können interne Ressourcen wie z. b. Speicher Konten so eingerichtet werden, dass nur der Zugriff durch Ressourcen ermöglicht wird, die sich auch auf dem Virtual Network befinden. Diese Firewall bietet ein zusätzliches Maß an Sicherheit, wenn die Schlüssel für dieses Speicherkonto kompromittiert werden könnten und Angreifer nicht in der Lage sind, die kompromittierten Schlüssel auszunutzen. Dies ist ein weiteres Beispiel für das Prinzip der geringsten Berechtigung.

Die Knoten in einem Azure Kubernetes-Cluster können genauso wie andere Ressourcen, die in Azure einheitlicher sind, an einem virtuellen Netzwerk teilnehmen. Diese Funktion wird als [Azure Container Networking-Schnittstelle](https://github.com/Azure/azure-container-networking/blob/master/docs/cni.md)bezeichnet. Tatsächlich weist Sie ein Subnetz innerhalb des virtuellen Netzwerks zu, dem virtuelle Computer und Container Images zugeordnet sind.

Wenn Sie den Weg zur Veranschaulichung des Prinzips der geringsten Rechte fortsetzen, muss nicht jede Ressource innerhalb einer Virtual Network mit allen anderen Ressourcen kommunizieren. Beispielsweise ist es in einer Anwendung, die eine Web-API über ein Speicherkonto und eine SQL-Datenbank bereitstellt, unwahrscheinlich, dass die Datenbank und das Speicherkonto miteinander kommunizieren müssen. Alle Daten, die zwischen Ihnen gemeinsam genutzt werden, durchlaufen die Webanwendung. Daher kann eine [Netzwerk Sicherheitsgruppe (NSG)](https://docs.microsoft.com/azure/virtual-network/security-overview) verwendet werden, um den Datenverkehr zwischen den beiden Diensten abzulehnen.

Eine Richtlinie, mit der die Kommunikation zwischen Ressourcen verweigert wird, kann sich als lästig erweisen. Dies gilt insbesondere für den Hintergrund der Verwendung von Azure ohne Datenverkehrs Einschränkungen. In einigen anderen Clouds ist das Konzept der Netzwerk Sicherheitsgruppen weitaus häufiger. Beispielsweise ist die Standard Richtlinie für AWS, dass Ressourcen nicht untereinander kommunizieren können, bis Sie durch Regeln in einer NSG aktiviert ist. Eine restriktivere Umgebung bietet zwar eine langsamere Entwicklung, bietet jedoch einen sichereren Standard. Die Verwendung geeigneter devops-Verfahren, insbesondere die Verwendung von [Azure Resource Manager oder TERRAFORM](infrastructure-as-code.md) zum Verwalten von Berechtigungen, kann die Steuerung der Regeln vereinfachen.

Virtuelle Netzwerke können auch beim Einrichten der Kommunikation zwischen lokalen Ressourcen und cloudressourcen nützlich sein. Ein virtuelles privates Netzwerk kann verwendet werden, um die beiden Netzwerke nahtlos zu verbinden. Dies ermöglicht die Ausführung eines virtuellen Netzwerks ohne irgendeine Art von Gateway für Szenarien, in denen alle Benutzer auf dem Standort vorhanden sind. Es gibt eine Reihe von Technologien, die verwendet werden können, um dieses Netzwerk einzurichten. Die einfachste Möglichkeit ist die Verwendung eines [Site-to-Site-VPN](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%2fazure%2fvirtual-network%2ftoc.json#s2smulti) , das zwischen vielen Routern und Azure hergestellt werden kann. Der Datenverkehr wird über das Internet mit den gleichen Kosten pro Byte wie bei jedem anderen Datenverkehr verschlüsselt und getunniert. Für Szenarien, in denen mehr Bandbreite oder mehr Sicherheit wünschenswert ist, bietet Azure einen Dienst mit dem Namen [Express Route](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%2fazure%2fvirtual-network%2ftoc.json#ExpressRoute) , der eine private Verbindung zwischen einem lokalen Netzwerk und Azure verwendet. Es ist kostspieliger und schwerer zu erstellen, aber auch sicherer.

## <a name="role-based-access-control-for-restricting-access-to-azure-resources"></a>Rollenbasierte Zugriffs Steuerung zum Einschränken des Zugriffs auf Azure-Ressourcen

RBAC ist ein System, das eine Identität für Anwendungen bereitstellt, die in Azure ausgeführt werden. Anwendungen können auf Ressourcen zugreifen, die diese Identität anstelle von oder zusätzlich zur Verwendung von Schlüsseln oder Kenn Wörtern verwenden.

## <a name="security-principals"></a>Sicherheits Prinzipale

Die erste Komponente in RBAC ist ein Sicherheits Prinzipal. Ein Sicherheits Prinzipal kann ein Benutzer, eine Gruppe, ein Dienst Prinzipal oder eine verwaltete Identität sein.

![Abbildung 10-2 verschiedene Typen von Sicherheits Prinzipale](./media/rbac-security-principal.png)
**Abbildung 10-2**. Verschiedene Typen von Sicherheits Prinzipale.

- Benutzer: jeder Benutzer, der über ein Konto in Azure Active Directory verfügt, ist ein Benutzer.
- Gruppieren: eine Sammlung von Benutzern aus Azure Active Directory. Als Mitglied einer Gruppe nimmt ein Benutzer zusätzlich zu seinen eigenen Rollen die Rollen dieser Gruppe an.
- Dienst Prinzipal: eine Sicherheitsidentität, unter der Dienste oder Anwendungen ausgeführt werden.
- Verwaltete Identität: eine Azure Active Directory Identität, die von Azure verwaltet wird. Verwaltete Identitäten werden in der Regel verwendet, wenn Cloud-Anwendungen entwickelt werden, die die Anmelde Informationen für die Authentifizierung bei Azure-Diensten verwalten.

Der Sicherheits Prinzipal kann auf die meisten Ressourcen angewendet werden. Dies bedeutet, dass es möglich ist, einem Container, der in Azure Kubernetes ausgeführt wird, einen Sicherheits Prinzipal zuzuweisen, sodass er auf in Key Vault gespeicherte Geheimnisse zugreifen kann. Eine Azure-Funktion könnte eine Berechtigung akzeptieren, damit Sie mit einer Active Directory Instanz kommunizieren kann, um ein JWT für einen aufrufenden Benutzer zu überprüfen. Nachdem Dienste mit einem Dienst Prinzipal aktiviert wurden, können Ihre Berechtigungen mithilfe von Rollen und Bereichen granulär verwaltet werden.

## <a name="roles"></a>Rollen

Ein Sicherheits Prinzipal kann zahlreiche Rollen übernehmen oder bei Verwendung einer eher in der Analogie verwendeten Analogie viele Hüte belegen. Jede Rolle definiert eine Reihe von Berechtigungen, z. b. "Lesen von Nachrichten von Azure Service Bus Endpunkts". Der effektive Berechtigungs Satz eines Sicherheits Prinzipals ist die Kombination aller Berechtigungen, die allen Rollen zugewiesen sind, die der Sicherheits Prinzipal besitzt. Azure verfügt über eine große Anzahl integrierter Rollen, und Benutzer können Ihre eigenen Rollen definieren.

![Abbildung 10-3 RBAC-Rollen Definitionen](./media/rbac-role-definition.png)
**Abbildung 10-3**. RBAC-Rollen Definitionen.

In Azure integriert ist auch eine Reihe von Rollen auf hoher Ebene, z. b. Besitzer, Mitwirkender, Leser und Benutzerkonto Administrator. Mit der Rolle "Besitzer" kann ein Sicherheits Prinzipal auf alle Ressourcen zugreifen und anderen Personen Berechtigungen zuweisen. Ein Mitwirkender hat dieselbe Zugriffsebene für alle Ressourcen, aber er kann keine Berechtigungen zuweisen. Ein Leser kann nur vorhandene Azure-Ressourcen anzeigen, und ein Benutzerkonto Administrator kann den Zugriff auf Azure-Ressourcen verwalten.

Präzisetere integrierte Rollen, z. b. [Mitwirkender von DNS-Zonen](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles#dns-zone-contributor) , haben Rechte, die auf einen einzelnen Dienst beschränkt sind Sicherheits Prinzipale können eine beliebige Anzahl von Rollen annehmen.

## <a name="scopes"></a>Bereiche

Rollen können auf einen eingeschränkten Satz von Ressourcen in Azure angewendet werden. Wenn Sie z. b. den Gültigkeitsbereich auf das vorherige Beispiel für das Lesen aus einer Service Bus Warteschlange anwenden, können Sie die Berechtigung auf eine einzelne Warteschlange einschränken: "Nachrichten von Azure Service Bus Endpunkt `blah.servicebus.windows.net/queue1`lesen"

Der Bereich kann so schmal wie eine einzelne Ressource sein oder auf eine gesamte Ressourcengruppe, ein Abonnement oder sogar auf eine Verwaltungsgruppe angewendet werden.

Beim Testen, ob ein Sicherheits Prinzipal über eine bestimmte Berechtigung verfügt, wird die Kombination von Rolle und Bereich berücksichtigt. Diese Kombination bietet einen leistungsfähigen Autorisierungs Mechanismus.

## <a name="deny"></a>Verweigern

Bisher waren nur "zulassen"-Regeln für die RBAC zulässig. Dieses Verhalten hat das Erstellen einiger Bereiche erschwert. So kann z. b. ein Sicherheits Prinzipal Zugriff auf alle Speicher Konten, außer auf einen, gewährt werden, um einer potenziell unendlichen Liste von Speicher Konten explizite Berechtigungen zu erteilen. Jedes Mal, wenn ein neues Speicherkonto erstellt wurde, muss es dieser Liste von Konten hinzugefügt werden. Dies erforderte einen Verwaltungsaufwand, der sicherlich nicht wünschenswert war.

Ablehnungs Regeln haben Vorrang vor Zulassungsregeln. Die Darstellung des gleichen "allow all with a"-Bereichs kann nun wie folgt dargestellt werden: "All zulassen" und "Deny this one this". Ablehnungs Regeln vereinfachen die Verwaltung nicht nur, sondern ermöglichen zusätzlich sichere Ressourcen, indem der Zugriff auf alle verweigert wird.

## <a name="checking-access"></a>Überprüfen des Zugriffs

Wie Sie sich vorstellen können, kann es schwierig sein, die effektive Berechtigung eines Dienst Prinzipals zu ermitteln, wenn eine große Anzahl von Rollen und Bereichen vorhanden ist. Das Anheften von Ablehnungs Regeln wird nur zur Erhöhung der Komplexität dienen. Glücklicherweise gibt es einen Berechtigungs Rechner, der die effektiven Berechtigungen für jeden Dienst Prinzipal anzeigen kann. Sie befindet sich in der Regel auf der Registerkarte IAM im Portal, wie in Abbildung 10-3 dargestellt.

![Abbildung 10-4 Berechtigungs Rechner für eine APP Service-](./media/check-rbac.png)
**Abbildung 10-4**. Der Berechtigungs Rechner für einen app Service.

## <a name="securing-secrets"></a>Sichern von Geheimnissen

Kenn Wörter und Zertifikate sind ein gängiger Angriffsvektor für Angreifer. Die Kenn Wort Absturz Hardware kann einen Brute-Force-Angriff durchführen und versuchen, Milliarden von Kenn Wörtern pro Sekunde zu erraten. Daher ist es wichtig, dass die Kenn Wörter, die für den Zugriff auf Ressourcen verwendet werden, stark sind und eine große Bandbreite an Zeichen aufweisen. Diese Kenn Wörter sind genau die Art von Kenn Wörtern, die sich beinahe nicht merken. Glücklicherweise müssen die Kenn Wörter in Azure von keinem menschlichen Benutzer bekannt sein.

Viele Sicherheits [Experten empfehlen](https://www.troyhunt.com/password-managers-dont-have-to-be-perfect-they-just-have-to-be-better-than-not-having-one/) , dass die Verwendung eines Kennwort-Managers zum Aufbewahren Ihrer eigenen Kenn Wörter die beste Vorgehensweise ist. Obwohl Sie Ihre Kenn Wörter an einem Ort zentralisiert, können Sie auch sehr komplexe Kenn Wörter verwenden und sicherstellen, dass Sie für jedes Konto eindeutig sind. Das gleiche System ist in Azure vorhanden: ein zentraler Speicher für Geheimnisse.

## <a name="azure-key-vault"></a>Azure Key Vault

Azure Key Vault bietet einen zentralisierten Speicherort zum Speichern von Kenn Wörtern für Dinge wie Datenbanken, API-Schlüssel und Zertifikate. Sobald ein geheimer Schlüssel in den Tresor eingegeben wurde, wird er nie erneut angezeigt, und die Befehle zum Extrahieren und Anzeigen sind absichtlich kompliziert. Die Informationen in der Safe werden entweder mithilfe der Software Verschlüsselung oder mithilfe der von TPS 140-2 Level 2 validierten Hardware Sicherheitsmodule geschützt.

Der Zugriff auf den Schlüssel Tresor wird über rbacs bereitgestellt. Dies bedeutet, dass nicht nur ein Benutzer auf die Informationen im Tresor zugreifen kann. Nehmen wir an, eine Webanwendung möchte auf die in Azure Key Vault gespeicherte Datenbank-Verbindungs Zeichenfolge zugreifen. Anwendungen müssen mithilfe eines Dienst Prinzipals ausgeführt werden, um Zugriff zu erhalten. Unter dieser angenommenen Rolle können die geheimen Schlüssel aus dem sicheren gelesen werden. Es gibt eine Reihe unterschiedlicher Sicherheitseinstellungen, mit denen der Zugriff einer Anwendung auf den Tresor weiter eingeschränkt werden kann, sodass keine geheimen Schlüssel aktualisiert, sondern nur gelesen werden kann.

Der Zugriff auf den Schlüssel Tresor kann überwacht werden, um sicherzustellen, dass nur die erwarteten Anwendungen auf den Tresor zugreifen. Die Protokolle können wieder in Azure Monitor integriert werden, sodass Sie die Möglichkeit zum Einrichten von Warnungen erhalten, wenn unerwartete Bedingungen auftreten.

## <a name="kubernetes"></a>Kubernetes

In Kubernetes gibt es einen ähnlichen Dienst zum Verwalten von kleinen geheimen Informationen. Kubernetes Geheimnisse können über die typische `kubectl` ausführbare Datei festgelegt werden.

Das Erstellen eines Geheimnisses ist so einfach wie das Auffinden der Base64-Version der zu speichernden Werte:

```console
echo -n 'admin' | base64
YWRtaW4=
echo -n '1f2d1e2e67df' | base64
MWYyZDFlMmU2N2Rm
```

Fügen Sie es dann zu einer Geheimnis Datei mit dem Namen `secret.yml` hinzu, die etwa wie im folgenden Beispiel aussieht:

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

Zum Schluss kann diese Datei in Kubernetes geladen werden, indem der folgende Befehl ausgeführt wird:

```console
kubectl apply -f ./secret.yaml
```

Diese geheimen Schlüssel können dann in Volumes bereitgestellt oder für Container Prozesse über Umgebungsvariablen verfügbar gemacht werden. Der Ansatz der [12-stufigen App](https://12factor.net/) zum Entwickeln von Anwendungen schlägt vor, den kleinsten gemeinsamen Nenner zum Übertragen von Einstellungen an eine Anwendung zu verwenden. Umgebungsvariablen sind der kleinste gemeinsame Nenner, da Sie unabhängig vom Betriebssystem oder der Anwendung unterstützt werden.

Eine Alternative zur Verwendung der integrierten Kubernetes-Geheimnisse besteht darin, innerhalb von Kubernetes auf die geheimen Schlüssel in Azure Key Vault zuzugreifen. Die einfachste Möglichkeit hierfür ist, dem Container eine RBAC-Rolle zuzuweisen, um geheime Schlüssel zu laden. Die Anwendung kann dann die Azure Key Vault-APIs verwenden, um auf die geheimen Schlüssel zuzugreifen. Dieser Ansatz erfordert jedoch Änderungen am Code und befolgt nicht das Muster der Verwendung von Umgebungsvariablen. Stattdessen ist es möglich, Werte in einen Container einzufügen, indem der [Azure Key Vault injetor](https://mrdevops.io/introducing-azure-key-vault-to-kubernetes-931f82364354)verwendet wird. Diese Vorgehensweise ist sicherer als die Verwendung der Kubernetes-Geheimnisse direkt, da Benutzer im Cluster darauf zugreifen können.

## <a name="encryption-in-transit-and-at-rest"></a>Verschlüsselung während der Übertragung und im Ruhezustand

Die Sicherheit der Daten ist wichtig, unabhängig davon, ob Sie sich auf einem Datenträger befinden oder zwischen verschiedenen Diensten wechseln. Die effektivste Methode, Daten von einem Verlust zu bewahren, besteht darin, Sie in ein Format zu verschlüsseln, das von anderen nicht einfach gelesen werden kann. Azure unterstützt eine große Bandbreite an Verschlüsselungsoptionen.

### <a name="in-transit"></a>Während der Übertragung

Es gibt mehrere Möglichkeiten, den Datenverkehr im Netzwerk in Azure zu verschlüsseln. Der Zugriff auf Azure-Dienste erfolgt in der Regel über Verbindungen, die Transport Layer Security (TLS) verwenden. Beispielsweise sind für alle Verbindungen mit den Azure-APIs TLS-Verbindungen erforderlich. Gleichermaßen können Verbindungen mit Endpunkten in Azure Storage nur über TLS-verschlüsselte Verbindungen verwendet werden.

TLS ist ein kompliziertes Protokoll, und es ist einfach zu wissen, dass die Verbindung TLS verwendet, nicht ausreichen, um die Sicherheit sicherzustellen. Beispielsweise ist TLS 1,0 chronisch unsicher, und TLS 1,1 ist nicht viel besser. Auch innerhalb der Versionen von TLS gibt es verschiedene Einstellungen, mit denen die Verbindungen leichter entschlüsselt werden können. Die beste Vorgehensweise besteht darin, zu überprüfen, ob die Server Verbindung aktuelle und ordnungsgemäß konfigurierte Protokolle verwendet.

Diese Überprüfung kann von einem externen Dienst wie dem SSL-Server Test von SSL Labs durchgeführt werden. Ein Testlauf für einen typischen Azure-Endpunkt, in diesem Fall ein Service Bus-Endpunkt, ergibt eine nahezu perfekte Bewertung eines.

Auch Dienste wie Azure SQL-Datenbanken verwenden die TLS-Verschlüsselung, um die Daten zu verbergen. Der interessante Teil der Verschlüsselung der Daten während der Übertragung mithilfe von TLS besteht darin, dass es nicht möglich ist, auch für Microsoft die Verbindung zwischen Computern zu überwachen, auf denen TLS ausgeführt wird. Dies sollte für Unternehmen sorgen, dass Ihre Daten von einem ordnungsgemäßen Microsoft-oder sogar einem Zustands Akteur mit mehr Ressourcen als dem Standard Angreifer gefährdet werden können.

![Abbildung 10-5 der Bericht "SSL Labs" zeigt eine Bewertung eines für einen Service Bus Endpunkt an.](./media/ssl-report.png)
**Abbildung 10-5**. Der Bericht "SSL Labs" zeigt die Bewertung eines für einen Service Bus Endpunkt an.

Diese Verschlüsselungs Stufe ist nicht für die gesamte Zeit ausreichend, Sie sollte jedoch sicher sein, dass Azure TLS-Verbindungen sehr sicher sind. Azure wird seine Sicherheitsstandards weiterentwickeln, wenn die Verschlüsselung verbessert wird. Es ist gut zu wissen, dass es jemanden gibt, der die Sicherheitsstandards überwacht und Azure bei der Verbesserung aktualisiert.

### <a name="at-rest"></a>Ruhende

In jeder Anwendung gibt es eine Reihe von stellen, an denen sich Daten auf dem Datenträger befinden. Der Anwendungscode selbst wird aus einem Speichermechanismus geladen. Die meisten Anwendungen verwenden auch eine Art von Datenbank, z. b. SQL Server, Cosmos DB oder sogar die erstaunlich Preis effiziente Table Storage. Diese Datenbanken verwenden alle stark verschlüsselten Speicher, um sicherzustellen, dass keine anderen Anwendungen als die Anwendungen mit den richtigen Berechtigungen Ihre Daten lesen können. Auch die System Operatoren können keine verschlüsselten Daten lesen. Daher können Kunden sicher sein, dass Ihre geheimen Informationen geheim bleiben.

### <a name="storage"></a>Speicher

Die Grundlage für einen Großteil von Azure ist die Azure Storage-Engine. Die Datenträger virtueller Computer werden auf Azure Storage bereitgestellt. Azure Kubernetes-Dienste werden auf virtuellen Computern ausgeführt, die auf Azure Storage gehostet werden. Sogar Server lose Technologien, wie Azure Functions-apps und Azure Container Instances, sind nicht auf dem Datenträger verfügbar, der Teil von Azure Storage ist.

Wenn Azure Storage gut verschlüsselt ist, wird eine Grundlage für die meisten anderen anderen Elemente für die Verschlüsselung bereit stehen. Azure Storage [ist](https://docs.microsoft.com/azure/storage/common/storage-service-encryption) mit der mit dem [fps 140-2](https://en.wikipedia.org/wiki/FIPS_140) kompatiblen [256-Bit-AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)verschlüsselt. Dies ist eine bekannte Verschlüsselungstechnologie, die in den letzten 20 oder so vielen Jahren eine umfassende akademische Überprüfung durchgeführt hat. Zurzeit gibt es keinen bekannten praktischen Angriff, der es einem Benutzer ohne Kenntnis des Schlüssels gestattet, Daten zu lesen, die von AES verschlüsselt wurden.

Standardmäßig werden die Schlüssel, die zum Verschlüsseln von Azure Storage verwendet werden, von Microsoft verwaltet. Es sind umfassende Schutzmaßnahmen vorhanden, um sicherzustellen, dass böswillige Zugriffe auf diese Schlüssel verhindert werden. Benutzer mit bestimmten Verschlüsselungs Anforderungen können jedoch auch [eigene Speicher Schlüssel bereitstellen](https://docs.microsoft.com/azure/storage/common/storage-encryption-keys-powershell) , die in Azure Key Vault verwaltet werden. Diese Schlüssel können jederzeit widerrufen werden, wodurch der Inhalt des Speicher Kontos auf diese Weise nicht mehr zugänglich ist.

Bei virtuellen Computern wird verschlüsselter Speicher verwendet, aber es ist möglich, eine andere Verschlüsselungs Ebene mithilfe von Technologien wie BitLocker unter Windows oder dm-crypt unter Linux bereitzustellen. Diese Technologien bedeuten, dass auch dann, wenn das Datenträger Abbild aus dem Speicher entfernt wurde, fast unmöglich wäre, es zu lesen.

### <a name="azure-sql"></a>Azure SQL

In Azure SQL gehostete Datenbanken verwenden eine Technologie namens [transparent Data Encryption (TDE)](/sql/relational-databases/security/encryption/transparent-data-encryption) , um sicherzustellen, dass die Daten verschlüsselt bleiben. Sie ist standardmäßig für alle neu erstellten SQL-Datenbanken aktiviert, muss jedoch manuell für Legacy Datenbanken aktiviert werden. TDE führt die Verschlüsselung und Entschlüsselung von Echtzeitdaten nicht nur für die Datenbank, sondern auch für die Sicherungen und Transaktionsprotokolle aus.

Die Verschlüsselungs Parameter werden in der `master`-Datenbank gespeichert und beim Start für die verbleibenden Vorgänge in den Arbeitsspeicher gelesen. Dies bedeutet, dass die `master` Datenbank unverschlüsselt bleiben muss. Der tatsächliche Schlüssel wird von Microsoft verwaltet. Benutzer mit strengen Sicherheitsanforderungen können jedoch ihren eigenen Schlüssel in Key Vault auf die gleiche Weise wie für Azure Storage bereitstellen. Der Key Vault stellt für Dienste wie die Schlüssel Rotation und die Sperrung bereit.

Der "transparente" Teil von TDS ergibt sich aus der Tatsache, dass keine Client Änderungen erforderlich sind, um eine verschlüsselte Datenbank zu verwenden. Obwohl dieser Ansatz eine gute Sicherheit bietet, ist das Verlust des Daten Bank Kennworts ausreichend, damit Benutzer die Daten entschlüsseln können. Es gibt einen weiteren Ansatz, bei dem einzelne Spalten oder Tabellen in einer Datenbank verschlüsselt werden. [Always Encrypted](https://docs.microsoft.com/azure/sql-database/sql-database-always-encrypted-azure-key-vault) stellt sicher, dass die verschlüsselten Daten zu keinem Zeitpunkt als Klartext innerhalb der Datenbank angezeigt werden.

Das Einrichten dieser Verschlüsselungs Stufe erfordert die Ausführung über einen Assistenten in SQL Server Management Studio, um die Art der Verschlüsselung auszuwählen, und wo in Key Vault die zugeordneten Schlüssel gespeichert werden sollen.

in ![Abbildung 10-6 Auswählen von Spalten in einer Tabelle, die mit Always Encrypted](./media/always-encrypted.png)
**Abbildung 10-6**verschlüsselt werden sollen. Auswählen von Spalten in einer Tabelle, die mit Always Encrypted verschlüsselt werden soll.

Client Anwendungen, die Informationen aus diesen verschlüsselten Spalten lesen, müssen besondere Berechtigungen zum Lesen verschlüsselter Daten gewähren. Verbindungs Zeichenfolgen müssen mit `Column Encryption Setting=Enabled` aktualisiert werden, und Client Anmelde Informationen müssen vom Key Vault abgerufen werden. Der SQL Server Client muss dann mit den Spalten Verschlüsselungsschlüsseln in der Liste angezeigt werden. Sobald dies abgeschlossen ist, verwenden die verbleibenden Aktionen die Standardschnittstellen für den SQL-Client. Das heißt, Tools wie dapperund Entity Framework, die auf dem SQL-Client basieren, funktionieren weiterhin ohne Änderungen. Always Encrypted ist möglicherweise noch nicht für alle SQL Server Treiber in jeder Sprache verfügbar.

Die Kombination von TDE und Always encrypted, die beide mit Client spezifischen Schlüsseln verwendet werden können, stellt sicher, dass auch die höchsten Verschlüsselungs Anforderungen unterstützt werden.

### <a name="cosmos-db"></a>Cosmos DB

Cosmos DB ist die neueste von Microsoft in Azure bereitgestellte Datenbank. Es wurde von Grund auf für Sicherheit und Kryptografie entwickelt. Die AES-256-Bit-Verschlüsselung ist standardmäßig für alle Cosmos DB-Datenbanken und kann nicht deaktiviert werden. Gekoppelt mit der TLS 1,2-Anforderung für die Kommunikation wird die gesamte Speicherlösung verschlüsselt.

![Abbildung 10-7 der Daten Verschlüsselungs Fluss innerhalb Cosmos DB](./media/cosmos-encryption.png)
**Abbildung 10-7**. Der Daten Verschlüsselungs Fluss in Cosmos DB.

Obwohl Cosmos DB nicht für die Bereitstellung von Kunden Verschlüsselungsschlüsseln bereitstellt, hat das Team bedeutende Arbeiten durchgeführt, um sicherzustellen, dass es ohne das PCI-DSS-kompatibel ist. Cosmos DB unterstützt auch keine Art von Single Column Encryption, ähnlich wie die Always Encrypted von Azure SQL.

## <a name="keeping-secure"></a>Sicherheit bewahren

Azure verfügt über alle Tools, die Sie zum Freigeben eines äußerst sicheren Produkts benötigen. Eine Kette ist jedoch nur so stark wie ihr schwächstes Glied. Wenn die Anwendungen, die auf Azure bereitgestellt werden, nicht mit einer ordnungsgemäßen Sicherheits Denkweise und guten Sicherheits Überwachungen entwickelt wurden, werden Sie zur schwachen Verknüpfung in der Kette. Es gibt viele hervor artige Statische Analysetools, Verschlüsselungs Bibliotheken und Sicherheitsmethoden, mit denen sichergestellt werden kann, dass die in Azure installierte Software so sicher wie Azure selbst ist. Beispiele hierfür sind [Statische Analysetools](https://www.whitesourcesoftware.com/), [Verschlüsselungs Bibliotheken](https://www.libressl.org/)und [Sicherheitsmethoden](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/).

>[!div class="step-by-step"]
>[Zurück](security.md)
>[Weiter](devops.md)
