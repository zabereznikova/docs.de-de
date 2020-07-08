---
title: Übersicht über .NET Framework
description: .NET Framework ist eine Technologie, die die Erstellung und Ausführung von Windows-Apps und -Webdiensten unterstützt.
ms.date: 03/30/2017
helpviewer_keywords:
- application development [.NET Framework]
- common language runtime
- common language runtime, about
- common language runtime, overview
ms.assetid: 29848c96-fc36-462d-8072-ba223a40b697
ms.openlocfilehash: 6beedb8e3fd03049cd58ce1d2dac78d1adb820ef
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618752"
---
# <a name="overview-of-net-framework"></a>Übersicht über .NET Framework

.NET Framework ist eine Technologie, die die Erstellung und Ausführung von Windows-Apps und Webdiensten unterstützt. .NET Framework wurde im Hinblick auf folgende Zielsetzungen entwickelt:

- Bereitstellung einer konsistenten, objektorientierten Programmierumgebung, in der Objektcode gespeichert wird. Die Ausführung erfolgt dann entweder lokal oder über Remotezugriff bzw. lokal mit Verteilung über das Web.

- Bereitstellung einer Codeausführungsumgebung, mit der Konflikte bei der Softwarebereitstellung und Versionskonflikte auf ein Minimum beschränkt werden.

- Bereitstellung einer Codeausführungsumgebung, die eine sichere Ausführung ermöglicht, und zwar auch von Code, der von unbekannten oder nur halb-vertrauenswürdigen Dritten erstellt wurde.

- Bereitstellung einer Codeausführungsumgebung, die nicht mehr die bei interpretations- oder skriptbasierten Umgebungen auftretenden Leistungsprobleme aufweist.

- Schaffung einer konsistenten Entwicklungsumgebung für die verschiedensten Typen von Apps, wie beispielsweise Windows- und webbasierte Apps.

- Aufbau der gesamten Kommunikation auf Industriestandards, um die Integration von Code, der auf .NET Framework basiert, in jeden anderen Code zu gewährleisten.

> [!NOTE]
> Eine allgemeine Einführung in .NET Framework für Benutzer und Entwickler erhalten Sie unter [Erste Schritte](index.md).

.NET Framework besteht aus der Common Language Runtime (CLR) und der .NET Framework-Klassenbibliothek. .NET Framework setzt auf der Common Language Runtime auf. Stellen Sie sich die Common Language Runtime als Agent vor, der zum Ausführungszeitpunkt Code verwaltet sowie Basisdienste wie Speicherverwaltung, Threadverwaltung und Remoting bereitstellt. Er erzwingt gleichzeitig strikte Typsicherheit und andere Formen der Codegenauigkeit, mit denen Sicherheit und Zuverlässigkeit unterstützt werden. Das Konzept der Codeverwaltung ist ein fundamentales Prinzip der Laufzeitumgebung. Code, der die Laufzeit zum Ziel hat, wird als verwalteter Code bezeichnet, während Code, der nicht auf die Laufzeit abzielt, als nicht verwalteter Code gilt. Die Klassenbibliothek, ist eine umfassende, objektorientierte Auflistung wiederverwendbarer Typen für die Entwicklung vielfältiger Apps, z. B. solcher mit herkömmlicher Befehlszeile oder grafischer Benutzeroberfläche (GUI), bis hin zu Apps, die auf den neuesten Innovationen von ASP.NET, z. B. Web Forms und XML-Webdiensten, basieren.

.NET Framework kann von nicht verwalteten Komponenten gehostet werden, durch die die Common Language Runtime in die Prozesse geladen und die Ausführung verwalteten Codes initiiert wird. So entsteht eine Softwareumgebung, in der sowohl verwaltete als auch nicht verwaltete Features genutzt werden. .NET Framework stellt nicht nur mehrere Laufzeithosts bereit, sondern unterstützt auch die Entwicklung von Laufzeithosts von Drittanbietern.

So dient beispielsweise ASP.NET als Laufzeithost und stellt eine skalierbare, serverseitige Umgebung für verwalteten Code bereit. ASP.NET arbeitet direkt mit der Common Language Runtime und aktiviert ASP.NET-Apps sowie XML-Webdienste, die weiter unten in diesem Artikel behandelt werden.

Internet Explorer ist ein Beispiel für eine nicht verwaltete App, die die Laufzeit (als MIME-Typerweiterung) hostet. Mit Internet Explorer als Laufzeithost können Sie verwaltete Komponenten oder Steuerelemente für Windows Forms in HTML-Dokumente einbetten. Ein derartiges Hosten der Laufzeit ermöglicht verwalteten mobilen Code, aber mit erheblichen Verbesserungen, wie sie nur verwalteter Code bietet, beispielsweise die Ausführung von halb-vertrauenswürdigem Code sowie isolierter Dateispeicher.

In der folgenden Abbildung ist die Beziehung der Common Language Runtime und der Klassenbibliothek zu den Apps und dem Gesamtsystem dargestellt. Außerdem geht aus der Abbildung hervor, wie verwalteter Code innerhalb einer größeren Architektur operiert.

![Screenshot mit einer Darstellung, wie verwalteter Code innerhalb einer größeren Architektur operiert.](./media/overview/language-runtime-class-library-relationship.gif)

In den folgenden Abschnitten werden die Hauptfunktionen von .NET Framework genauer beschrieben.

## <a name="features-of-the-common-language-runtime"></a>Features der Common Language Runtime

Die Common Language Runtime verwaltet Speicher, Thread- und Codeausführung, Überprüfung der Codesicherheit, Kompilierung und andere Systemdienste. Diese Features sind in den verwalteten Code integriert, der durch die Common Language Runtime ausgeführt wird.

Aus Sicherheitsgründen werden verwalteten Komponenten unterschiedliche Vertrauensstufen zugewiesen, die von mehreren Faktoren abhängen, zu denen auch der Ursprung (z. B. das Internet, ein Intranet oder ein lokaler Computer) zählt. Das bedeutet, dass eine verwaltete Komponente je nachdem auf Dateien und die Registrierung zugreifen bzw. andere sensible Funktionen ausführen kann oder ihr der Zugriff untersagt ist, selbst wenn sie in derselben aktiven App verwendet wird.

Durch die Implementierung des allgemeinen Typsystems (Common Type System; CTS), einer Infrastruktur mit strikter Typ- und Codeüberprüfung, erzwingt die Common Language Runtime außerdem die Coderobustheit. Durch das CTS wird sichergestellt, dass der gesamte verwaltete Code sich selbst beschreibt. Die verschieden Sprachcompiler von Microsoft und von Drittanbietern generieren verwalteten Code, der dem CTS entspricht. Dies bedeutet, dass verwalteter Code andere verwaltete Typen und Instanzen nutzen und gleichzeitig streng Typtreue und Typsicherheit erzwingen kann.

Außerdem werden durch eine verwaltete Laufzeitumgebung viele bekannte Softwareprobleme beseitigt. So verarbeitet die Common Language Runtime beispielsweise automatisch das Objektlayout, verwaltet Objektreferenzen und gibt diese wieder frei, wenn sie nicht mehr verwendet werden. Durch diese automatische Speicherverwaltung werden Speicherverluste und ungültige Speicherreferenzen, die beiden häufigsten App-Fehler, beseitigt.

Die Produktivität der Entwickler wird außerdem durch die Common Language Runtime erhöht. So können Programmierer beispielsweise Apps in der von ihnen bevorzugten Programmiersprache schreiben und trotzdem die Common Language Runtime, die Klassenbibliothek und die in anderen Sprachen von anderen Entwicklern geschriebenen Komponenten in vollem Umfang nutzen. Jeder Compileranbieter, der die Laufzeit zum Ziel hat, kann entsprechend vorgehen. Sprachcompiler, die .NET Framework zum Ziel haben, stellen die .NET Framework-Features bereits bestehendem Code in der jeweiligen Sprache zur Verfügung und erleichtern damit nicht unerheblich den Migrationsprozess für bestehende Apps.

Die Common Language Runtime wurde zwar für die Software von morgen entwickelt, unterstützt aber auch aktuelle und ältere Anwendungen. Durch die Interoperabilität zwischen verwaltetem und nicht verwaltetem Code können Entwickler weiterhin benötigte COM-Komponenten und DLLs verwenden.

Bei der Common Language Runtime wurde auch die Leistungssteigerung berücksichtigt. Obwohl die Common Language Runtime viele Standardlaufzeitdienste bereitstellt, wird verwalteter Code nicht interpretiert. Durch die JIT-Kompilierung, ein Feature für das Just-in-Time-Kompilieren (JIT), kann der gesamte verwaltete Code in der nativen Maschinensprache des jeweiligen Systems ausgeführt werden. Währenddessen verhindert die Speicherverwaltung die Speicherfragmentierung und erhöht zur weiteren Leistungssteigerung die lokalen Speicherverweise.

Schließlich kann die Common Language Runtime auch von hochleistungsfähigen, serverseitigen Apps wie Microsoft SQL Server und Internetinformationsdiensten (IIS) gehostet werden. Diese Infrastruktur bietet die Möglichkeit, Geschäftslogik mit verwaltetem Code zu schreiben und gleichzeitig die überlegene Leistungsfähigkeit der branchenweit besten Organisationsserver zu nutzen, die Laufzeithosting unterstützen.

## <a name="net-framework-class-library"></a>.NET Framework-Klassenbibliothek

Die .NET Framework-Klassenbibliothek ist eine Auflistung wiederverwendbarer Typen, die eng in die Common Language Runtime integriert sind. Die Klassenbibliothek ist objektorientiert und stellt Typen bereit, von denen Ihr eigener verwalteter Code Funktionen ableitet. Dadurch können Sie die .NET Framework-Typen problemlos verwenden und sich schneller mit den neuen Features von .NET Framework vertraut machen. Außerdem können Komponenten von Drittanbietern nahtlos in .NET Framework integriert werden.

So wird beispielsweise durch die Auflistungsklassen in .NET Framework ein Schnittstellensatz zur Entwicklung eigener Auflistungsklassen implementiert. Ihre Auflistungsklassen fügen sich nahtlos in die .NET Framework-Klassen ein.

Wie von einer objektorientierten Klassenbibliothek zu erwarten, lassen sich mit den .NET Framework-Typen viele gängige Programmieraufgaben erledigen, darunter Zeichenfolgenverwaltung, Datenerfassung, Datenbankkonnektivität und Dateizugriff. Neben diesen Typen für normale Aufgaben beinhaltet die Klassenbibliothek auch Typen, die verschiedene spezielle Entwicklungsszenarien unterstützen. Sie können NET Framework beispielsweise zur Entwicklung der folgenden Typen von Apps und Diensten verwenden:

- Konsolen-Apps Siehe [Erstellen von Konsolenanwendungen](../../standard/building-console-apps.md).

- GUI-Apps für Windows (Windows Forms) Siehe [Windows Forms](../winforms/index.md).

- Apps für Windows Presentation Foundation (WPF) Siehe [Windows Presentation Foundation](../wpf/index.md).

- ASP.NET-Apps Siehe [Webanwendungen mit ASP.NET](../develop-web-apps-with-aspnet.md).

- Windows-Dienste Siehe [Einführung in Windows-Dienstanwendungen](../windows-services/introduction-to-windows-service-applications.md).

- Dienstorientierte Apps mit Windows Communication Foundation (WCF) Siehe [Dienstorientierte Anwendungen mit WCF](../wcf/index.md).

- Workflowfähige Apps mit Windows Workflow Foundation (WF) Siehe [Windows Workflow Foundation](../windows-workflow-foundation/index.md).

Die Klassen für Windows Forms bestehen aus einem umfangreichen Satz wiederverwendbarer Typen, die die Entwicklung für Windows-GUIs erheblich vereinfachen. Beim Schreiben einer ASP.NET Web Form-Apps können diese Web Forms-Klassen verwendet werden.

## <a name="see-also"></a>Siehe auch

- [Systemanforderungen](system-requirements.md)
- [Installationshandbuch](../install/index.md)
- [Entwicklungshandbuch für .NET Framework](../development-guide.md)
- [Extras](../tools/index.md)
- [Beispiele und Tutorials](../../samples-and-tutorials/index.md)
- [.NET API-Browser](../../../api/index.md)
