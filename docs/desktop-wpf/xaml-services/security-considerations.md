---
title: XAML-Sicherheitsüberlegungen
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: 1864910b339c74e3033fb4d6d8baebffada1a4f8
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432917"
---
# <a name="xaml-security-considerations"></a>XAML-Sicherheitsüberlegungen

In diesem Artikel werden bewährte Methoden für die Sicherheit in Anwendungen beschrieben, wenn Sie XAML und .NET XAML Services API verwenden.

## <a name="untrusted-xaml-in-applications"></a>Nicht vertrauenswürdiges XAML in Anwendungen

Im weitesten Sinne ist nicht vertrauenswürdiges XAML eine XAML-Quelle, die Ihre Anwendung nicht ausdrücklich eingeschlossen oder ausgestoßen hat.

XAML, das in einer `resx`vertrauenswürdigen und signierten Assembly kompiliert oder als -type-Ressource gespeichert wird, ist nicht von Natur aus nicht vertrauenswürdig. Sie können dem XAML genauso vertrauen wie der Assembly als Ganzes. In den meisten Fällen befassen Sie sich nur mit den Vertrauensaspekten von losem XAML, einer XAML-Quelle, die Sie aus einem Stream oder anderen E/A-Nachrichten laden. Lose XAML ist keine bestimmte Komponente oder Funktion eines Anwendungsmodells mit einer Bereitstellungs- und Verpackungsinfrastruktur. Eine Assembly kann jedoch ein Verhalten implementieren, das das Laden von losem XAML umfasst.

Bei nicht vertrauenswürdigem XAML sollten Sie es im Allgemeinen so behandeln, als wäre es nicht vertrauenswürdiger Code. Verwenden Sie Sandboxing oder andere Metaphern, um zu verhindern, dass möglicherweise nicht vertrauenswürdige XAML auf Ihren vertrauenswürdigen Code zugreifen.

Die Art der XAML-Funktionen gibt XAML das Recht, Objekte zu erstellen und ihre Eigenschaften festzulegen. Zu diesen Funktionen gehören auch der Zugriff auf Typkonverter, das Zuordnen und `x:Code` Zugreifen auf Assemblys in der Anwendungsdomäne, die Verwendung von Markuperweiterungen, Blöcken usw.

Zusätzlich zu den Funktionen auf Sprachebene wird XAML für die UI-Definition in vielen Technologien verwendet. Das Laden von nicht vertrauenswürdigem XAML kann das Laden einer bösartigen Spoofing-Benutzeroberfläche bedeuten.

## <a name="sharing-context-between-readers-and-writers"></a>Freigeben von Kontext zwischen Lesern und Autoren

.NET XAML Services-Architektur für XAML-Reader und XAML-Writer erfordert häufig die Freigabe eines XAML-Readers für einen XAML-Writer oder einen freigegebenen XAML-Schemakontext. Wenn Sie XAML-Knotenschleifenlogik schreiben oder einen benutzerdefinierten Speicherpfad bereitstellen, ist möglicherweise die Freigabe von Objekten oder Kontexten erforderlich. Geben Sie XAML-Readerinstanzen, nicht standardmäßigen XAML-Schemakontext oder Einstellungen für XAML-Reader-/Writer-Klassen zwischen vertrauenswürdigem und nicht vertrauenswürdigem Code nicht gemeinsam.

Die meisten Szenarien und Vorgänge, die das Schreiben von XAML-Objekten für eine CLR-basierte Typsicherung beinhalten, können nur den standardmäßigen XAML-Schemakontext verwenden. Der standardmäßige XAML-Schemakontext enthält keine expliziten Einstellungen, die die volle Vertrauenswürdigkeit gefährden könnten. Es ist daher sicher, den Kontext zwischen vertrauenswürdigen und nicht vertrauenswürdigen XAML-Reader-/Writer-Komponenten gemeinsam zu nutzen. Wenn Sie dies jedoch tun, ist es immer noch eine <xref:System.AppDomain> bewährte Methode, solche Leser und Autoren in getrennten Bereichen zu halten, wobei einer von ihnen speziell für teilweise vertrauenswürdig gedacht/sandboxed ist.

## <a name="xaml-namespaces-and-assembly-trust"></a>XAML-Namespaces und Assembly-Vertrauensstellung

Die grundlegende nicht qualifizierte Syntax und Definition für die Interpretation einer benutzerdefinierten XAML-Namespacezuordnung zu einer Assembly unterscheidet nicht zwischen einer vertrauenswürdigen und einer nicht vertrauenswürdigen Assembly, die in die Anwendungsdomäne geladen wird. Daher ist es technisch möglich, dass eine nicht vertrauenswürdige Assembly die beabsichtigte XAML-Namespacezuordnung einer vertrauenswürdigen Assembly vortäuscht und die deklarierten Objekt- und Eigenschaftsinformationen einer XAML-Quelle erfasst. Wenn Sie Sicherheitsanforderungen haben, um diese Situation zu vermeiden, sollte die beabsichtigte XAML-Namespacezuordnung mit einer der folgenden Techniken erfolgen:

- Verwenden Sie einen vollqualifizierten Assemblynamen mit starkem Namen in jeder XAML-Namespacezuordnung, die vom XAML Ihrer Anwendung erstellt wird.

- Beschränken Sie die Assemblyzuordnung auf einen festen <xref:System.Xaml.XamlSchemaContext> Satz von Verweisassemblys, indem Sie eine bestimmte für Ihre XAML-Lesegeräte und XAML-Objektschreiber erstellen. Siehe <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.

## <a name="xaml-type-mapping-and-type-system-access"></a>XAML-Typzuordnung und Systemzugriff

XAML unterstützt ein eigenes Typsystem, das in vielerlei Hinsicht ein Peer ist, wie CLR das grundlegende CLR-Typsystem implementiert. Bei bestimmten Aspekten der Typbewissung, bei denen Sie Vertrauensentscheidungen zu einem Typ basierend auf seinen Typinformationen treffen, sollten Sie die Typinformationen in den CLR-Sicherungstypen aufschieben. Dies liegt daran, dass einige der spezifischen Berichtsfunktionen des XAML-Typsystems als virtuelle Methoden offen gelassen werden und daher nicht vollständig unter der Kontrolle der ursprünglichen .NET XAML Services-Implementierungen stehen. Diese Erweiterbarkeitspunkte sind vorhanden, da das XAML-Typsystem erweiterbar ist, um der Erweiterbarkeit von XAML selbst und seinen möglichen alternativen Typzuordnungsstrategien im Vergleich zur standardmäßigen CLR-gestützten Implementierung und dem standardmäßigen XAML-Schemakontext zu entsprechen. Weitere Informationen finden Sie in den spezifischen <xref:System.Xaml.XamlType> Hinweisen <xref:System.Xaml.XamlMember>zu mehreren Eigenschaften von und .

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xaml.Permissions.XamlAccessLevel>
