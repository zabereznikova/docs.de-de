---
title: XAML-Sicherheitsüberlegungen
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: 124310497cc2a8e8a816ba90b2c68a16ed342ae6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973448"
---
# <a name="xaml-security-considerations"></a>XAML-Sicherheitsüberlegungen
Dieses Thema beschreibt bewährte Methoden für die Sicherheit in Anwendungen, bei der Verwendung von XAML und .NET Framework-XAML-Dienste-API.  
  
## <a name="untrusted-xaml-in-applications"></a>Nicht vertrauenswürdige XAML in Anwendungen  
 In der Allgemein ausgedrückt ist nicht vertrauenswürdige XAML einer beliebigen XAML-Quelle, die Ihre Anwendung nicht ausdrücklich enthalten oder ausgeben.  
  
 XAML, die in kompiliert oder als gespeicherte eine `resx`-Typressource in einer vertrauenswürdigen und signierten Assembly ist nicht grundsätzlich nicht vertrauenswürdig. Sie können die XAML darauf verlassen, wie Sie die Assembly als Ganzes als vertrauenswürdig einstufen. In den meisten Fällen sind Sie nur die Aspekte der Vertrauenswürdigkeit von loose XAML, die eine XAML-Quelle ist, die Sie aus einem Stream oder andere e/a-laden kümmern. Loose XAML ist nicht an eine bestimmte Komponente oder ein Feature des ein Anwendungsmodell mit einer Bereitstellung und die paketerstellung-Infrastruktur. Eine Assembly kann jedoch ein Verhalten implementieren, die umfasst das Laden von loose XAML.  
  
 Für nicht vertrauenswürdige XAML sollten Sie es im Allgemeinen behandeln als handele es sich um nicht vertrauenswürdigem Code. Verwenden Sie Sandboxing oder andere Metaphern, um zu verhindern, dass möglicherweise nicht vertrauenswürdige XAML den Zugriff auf Ihr vertrauenswürdiger Code.  
  
 Die Art der XAML-Funktionen bietet das XAML das Recht zum Erstellen von Objekten und deren Eigenschaften festlegen. Diese Funktionen beinhalten auch den Zugriff auf Typkonverter, zuordnen und den Zugriff auf Assemblys in der Anwendungsdomäne, die Verwendung von Markuperweiterungen, `x:Code` Blöcke und So weiter.  
  
 Zusätzlich zu seiner Funktionen auf Sprachebene wird XAML zur Definition der Benutzeroberfläche in vielen Technologien verwendet. Laden nicht vertrauenswürdige XAML kann dies bedeuten, die eine böswillige spoofing-Benutzeroberfläche geladen.  
  
## <a name="sharing-context-between-readers-and-writers"></a>Freigeben von Kontext zwischen Readern und Writern  
 Die .NET Framework-XAML-Dienste-Architektur für XAML-Readern und XAML-Writern erfordert häufig einen XAML-Reader auf einem XAML-Writer oder eine freigegebene XAML-Schemakontext freigeben. Freigabe von Objekten oder Kontexten kann erforderlich sein, wenn Sie Schleifenlogik für XAML-Knoten schreiben und Bereitstellen eines benutzerdefinierten Pfad speichern. Sie sollten keine Instanzen der XAML-Reader, den nicht standardmäßigen XAML-Schemakontext oder für XAML-Reader/Writer-Klassen zwischen vertrauenswürdigen und nicht vertrauenswürdigen Code freigeben.  
  
 Die meisten Szenarien und Vorgänge im Zusammenhang mit XAML-Objekt für einen CLR-basierten Typ sichern schreiben können nur XAML-Standardschemakontext verwenden. Der Standard-XAML-Schemakontext umfasst keine explizit Einstellungen, die volle Vertrauenswürdigkeit gefährden könnten. Es ist daher sicher, den Kontext zwischen vertrauenswürdigen und nicht vertrauenswürdige XAML-Reader-/Writer-Komponenten gemeinsam verwenden. Wenn Sie dies tun, es ist jedoch immer noch eine bewährte Methode, behalten Sie diese Reader und Writer in separaten <xref:System.AppDomain> Bereiche, mit einem von ihnen explizit beabsichtigt/Sandbox für teilweise Vertrauenswürdigkeit.  
  
## <a name="xaml-namespaces-and-assembly-trust"></a>XAML-Namespaces und die Vertrauensstellung einer Assembly  
 Die grundlegende nicht qualifizierte Syntax und die Definition für die Interpretation von XAML auf einer benutzerdefinierten XAML-Namespace-Zuordnung zu einer Assembly unterscheidet nicht zwischen einem vertrauenswürdigen und nicht vertrauenswürdigen Assembly als in der Anwendungsdomäne geladen. Daher ist es technisch möglich ist, für eine nicht vertrauenswürdige Assembly das Spoofing von einer vertrauenswürdigen Assembly beabsichtigten XAML-Namespace-Zuordnung und das deklarierte Objekt einer XAML-Quelle und Eigenschafteninformationen erfassen. Ihre sicherheitsanforderungen diese Situation vermeiden können muss Ihre beabsichtigte XAML-Namespace-Zuordnung mit einer der folgenden Methoden erstellt werden:  
  
-   Verwenden Sie einen vollqualifizierten Assemblynamen mit starken Namen in eine beliebige XAML-Namespace-Zuordnung, die von Ihrer Anwendung XAML an.  
  
-   Beschränken Sie die Assembly, die auf einen festen Satz von Verweisassemblys, die durch das Erstellen eines bestimmtes Zuordnung <xref:System.Xaml.XamlSchemaContext> für Ihre XAML-Readern und XAML Objekt-Writer. Siehe <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.  
  
## <a name="xaml-type-mapping-and-type-system-access"></a>XAML-Typzuordnung und Systemzugriff Typ  
 XAML unterstützt eine eigene Typsystem, das in vielerlei Hinsicht gleichberechtigt ist, wie die CLR die einfache CLR-Typsystems implementiert. Für bestimmte Aspekte Typ wissen, wo Sie Entscheidungen zur Vertrauenswürdigkeit zu einem Typ, der basierend auf seine Typinformationen vornehmen, sollten Sie jedoch, um die Typinformationen in der CLR Unterstützungstypen verzögern. Dies ist, da einige der spezifischen reporting-Funktionen des XAML-Typsystems als virtuelle Methoden offen gelassen werden und sind daher nicht vollständig unter der Kontrolle der ursprünglichen Implementierungen von .NET Framework-XAML-Dienste. Diese Erweiterungspunkte vorhanden sein, da das XAML-Typsystem entsprechend der Erweiterbarkeit des XAML selbst und seine möglichen Alternativen Typzuordnung Strategien im Vergleich zu den CLR-gesicherten Standardimplementierung und XAML-Standardschemakontext erweiterbar ist. Weitere Informationen finden Sie unter der Hinweise auf einige der Eigenschaften von <xref:System.Xaml.XamlType> und <xref:System.Xaml.XamlMember>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xaml.Permissions.XamlAccessLevel>
