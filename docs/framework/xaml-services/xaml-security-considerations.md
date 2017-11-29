---
title: "XAML-Sicherheitsüberlegungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
caps.latest.revision: "7"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 59d0b835a0de3e84e2cb6e77ed368511bfe21b19
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-security-considerations"></a>XAML-Sicherheitsüberlegungen
Dieses Thema beschreibt bewährte Methoden für die Sicherheit in Anwendungen, bei der Verwendung von XAML und .NET Framework-XAML-Dienste-API.  
  
## <a name="untrusted-xaml-in-applications"></a>Nicht vertrauenswürdige XAML in Anwendungen  
 In den meisten allgemeinen Sinn ist nicht vertrauenswürdige XAML alle XAML-Quelle, die Ihre Anwendung nicht ausdrücklich einschließen oder ausgegeben.  
  
 XAML, die in kompiliert oder als gespeicherten ist eine `resx`-Typ der Ressource in einer vertrauenswürdigen und signierten Assembly ist nicht grundsätzlich nicht vertrauenswürdig. Sie können den XAML-Code als vertrauenswürdig einstufen, wie Sie die Assembly als Ganzes als vertrauenswürdig einstufen. In den meisten Fällen sind Sie nur die Aspekte der Vertrauenswürdigkeit von loose XAML, also eine XAML-Quelle, die Sie aus einem Stream oder andere e/a-laden dürfte. Loose XAML ist nicht an eine bestimmte Komponente oder eine Funktion eines Modells Anwendung mit einer Bereitstellung und die Verpackung-Infrastruktur. Eine Assembly kann jedoch ein Verhalten implementieren, das Laden von loose XAML umfasst.  
  
 Für nicht vertrauenswürdige XAML sollten Sie es im Allgemeinen behandeln als handele es sich um nicht vertrauenswürdigem Code. Verwenden Sie Sandboxing oder andere Metaphern, um zu verhindern, dass möglicherweise nicht vertrauenswürdiges XAML zugreifen auf Ihren vertrauenswürdigen Code.  
  
 Die Art der Verwendung von XAML-Funktionen ermöglicht dem XAML-Code das Recht zum Erstellen von Objekten und ihre Eigenschaften festlegen. Diese Funktionen auch sind der Zugriff auf den Einsatz von Typkonvertern, zuordnen und den Zugriff auf Assemblys in der Anwendungsdomäne, die Verwendung von Markuperweiterungen, `x:Code` Blöcke und So weiter.  
  
 XAML wird zusätzlich zu seiner Funktionen auf Sprachebene für UI-Definition in vielen Technologien verwendet. Laden von nicht vertrauenswürdigen XAML kann dies bedeuten, laden eine böswillige spoofing-Benutzeroberfläche.  
  
## <a name="sharing-context-between-readers-and-writers"></a>Freigeben von Kontext zwischen Readern und Writern  
 Die .NET Framework XAML Services-Architektur für XAML-Readern und XAML-Writer erfordert häufig die Freigabe eines XAML-Readers ein XAML-Writer oder einen freigegebenen XAML-Schemakontext. Freigabe von Objekten oder Kontexten kann erforderlich sein, wenn Sie Schleifenlogik für XAML-Knoten schreiben oder Bereitstellen eines benutzerdefinierten Speicherpfad. Sie sollten die Verwendung von XAML-Reader-Instanzen, nicht standardmäßigen XAML-Schemakontext oder Einstellungen für Klassen mit XAML Reader/Writer zwischen vertrauenswürdigen und nicht vertrauenswürdigen Code nicht freigeben.  
  
 Die meisten Szenarien und Vorgänge im Zusammenhang mit XAML-Objekt für einen CLR-basierten Typ sichern schreiben können nur XAML-Standardschemakontext verwenden. Die Verwendung von XAML-Standardschemakontext umfasst nicht explizit Einstellungen, die volle Vertrauenswürdigkeit gefährden können. Es ist daher sicher, Kontext zwischen vertrauenswürdigen und nicht vertrauenswürdige XAML-Reader/Writer Komponenten gemeinsam verwenden. Wenn Sie so vorgehen, es ist jedoch immer noch eine bewährte Methode, behalten Sie diese Reader und Writer in separaten <xref:System.AppDomain> Bereiche, mit einem von ihnen ausdrücklich vorgesehen/Sandbox für teilweise Vertrauenswürdigkeit.  
  
## <a name="xaml-namespaces-and-assembly-trust"></a>Verwendung von XAML-Namespaces und die Vertrauensstellung einer Assembly  
 Die grundlegende nicht qualifizierte Syntax und die Definition für die Interpretation einer benutzerdefinierten XAML-Namespacezuordnung auf eine Assembly in XAML unterscheidet nicht zwischen einer vertrauenswürdigen und nicht vertrauenswürdigen Assembly in die Anwendungsdomäne geladen. Daher ist es technisch möglich, dass eine nicht vertrauenswürdige Assembly Spoofing beabsichtigten Verwendung von XAML-Namespacezuordnung eine vertrauenswürdige Assembly und das deklarierte Objekt von einem XAML-Quelle und Informationen zu erfassen. Haben sicherheitsanforderungen, um diese Situation zu vermeiden, muss die Ihrer beabsichtigten Verwendung von XAML-Namespacezuordnung mithilfe einer der folgenden Methoden erstellt werden:  
  
-   Verwenden Sie einen vollqualifizierten Assemblynamen mit starken Namen in eine beliebige XAML-Namespacezuordnung von der Anwendung vorgenommen werden.  
  
-   Beschränken Sie die Assembly, die auf einen festen Satz von Verweisassemblys, durch das Erstellen eines bestimmtes Zuordnung <xref:System.Xaml.XamlSchemaContext> für die XAML-Readern und XAML-Objektwriter. Siehe <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.  
  
## <a name="xaml-type-mapping-and-type-system-access"></a>Verwendung von XAML-Typzuordnung und Systemzugriff Typ  
 XAML unterstützt eine eigene Typsystems, bei dem in vielerlei Hinsicht ein Peer ist-zu-wie die grundlegenden CLR-Typsystem von CLR implementiert. Für bestimmte Aspekte Typ wissen, wo Sie Entscheidungen zur Vertrauenswürdigkeit der über einen Typ basierend auf seiner Typinformationen vornehmen, sollten Sie jedoch auf die Typinformationen in der CLR Unterstützungstypen verzögern. Dies ist, da einige der spezifischen Berichtsfunktionen der XAML-Typsystem als virtuelle Methoden geöffnet bleiben und sind daher nicht vollständig von der ursprünglichen Implementierungen von .NET Framework XAML Services kontrolliert. Diese Erweiterungspunkte genutzt, vorhanden sind, da das XAML-Typsystem erweiterbar ist, um die Erweiterbarkeit des XAML selbst und seine möglichen Alternativen Typzuordnung Strategien im Vergleich zu den CLR-gesicherten Standardimplementierung und XAML-Standardschemakontext abzugleichen. Weitere Informationen finden Sie spezifische Hinweise auf einige der Eigenschaften von <xref:System.Xaml.XamlType> und <xref:System.Xaml.XamlMember>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xaml.Permissions.XamlAccessLevel>
