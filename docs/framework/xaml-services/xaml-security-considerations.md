---
title: "XAML Security Considerations | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "security [XAML Services], .NET XAML services"
  - "XAML security [XAML Services]"
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# XAML Security Considerations
In diesem Thema werden bewährte Methoden für die Sicherheit in Anwendungen beim Verwenden von XAML und der .NET Framework\-XAML\-Dienste\-API beschrieben.  
  
## Nicht vertrauenswürdige XAML in Anwendungen  
 Allgemein ausgedrückt, ist nicht vertrauenswürdige XAML jede XAML\-Quelle, die die Anwendung nicht ausdrücklich eingeschlossen oder ausgegeben hat.  
  
 Als `resx`\-Ressource in einer vertrauenswürdigen und signierten Assembly kompiliertes oder gespeichertes XAML ist nicht grundsätzlich nicht vertrauenswürdig.  Sie können die XAML für ebenso vertrauenswürdig halten wie die Assembly als Ganzes.  In den meisten Fällen müssen Sie sich nur mit den Vertrauensstellungsaspekten von Loose XAML befassen, einer XAML\-Quelle, die Sie aus einem Stream oder anderer EA laden.  Loose XAML ist keine spezifische Komponente oder Funktion eines Anwendungsmodells mit einer Bereitstellungs\- und Verpackungsinfrastruktur.  Es ist jedoch möglich, dass eine Assembly ein Verhalten implementiert, das das Laden von Loose XAML beinhaltet.  
  
 Nicht vertrauenswürdige XAML sollten Sie im Allgemeinen genauso behandeln wie nicht vertrauenswürdigen Code.  Verwenden Sie Sandboxing oder andere Metaphern, um zu verhindern, dass möglicherweise nicht vertrauenswürdige XAML auf den vertrauenswürdigen Code zugreift.  
  
 Die Art von XAML\-Funktionen gibt der XAML das Recht, Objekte zu erstellen und ihre Eigenschaften festzulegen.  Diese Funktionen beinhalten auch den Zugriff auf Typkonverter, die Zuordnung von Assemblys und den Zugriff auf Assemblys in der Anwendungsdomäne, die Verwendung von Markuperweiterungen, `x:Code`\-Blöcke usw.  
  
 Neben den Funktionen auf Sprachebene wird XAML in vielen Technologien für die Benutzeroberflächendefinition verwendet.  Durch das Laden von nicht vertrauenswürdigem XAML wird möglicherweise eine schädliche Spoofing\-Benutzeroberfläche geladen.  
  
## Freigeben von Kontext zwischen Readern und Writern  
 Die .NET Framework\-XAML\-Dienste\-Architektur für XAML\-Reader und XAML\-Writer erfordert häufig die Freigabe eines XAML\-Readers für einen XAML\-Writer oder einen freigegebenen XAML\-Schemakontext.  Die Freigabe von Objekten oder Kontexten kann erforderlich sein, wenn Sie Schleifenlogik für XAML\-Knoten schreiben oder einen benutzerdefinierten Speicherpfad bereitstellen.  Sie sollten XAML\-Readerinstanzen, nicht standardmäßigen XAML\-Schemakontext oder Einstellungen für XAML\-Reader\-\/\-Writer\-Klassen zwischen vertrauenswürdigem und nicht vertrauenswürdigem Code nicht freigeben.  
  
 Die meisten Szenarios und Vorgänge, an denen die XAML\-Objekterstellung für eine CLR\-basierte Typunterstützung beteiligt ist, können nur den XAML\-Standardschemakontext verwenden.  Der XAML\-Standardschemakontext beinhaltet nicht explizit Einstellungen, die die volle Vertrauenswürdigkeit beeinträchtigen könnten.  Daher ist es sicher, Kontext zwischen vertrauenswürdigen und nicht vertrauenswürdigen XAML\-Reader\-\/Writer\-Komponenten freizugeben.  Dabei empfiehlt es sich jedoch dennoch, diese Reader und Writer in separaten <xref:System.AppDomain>\-Bereichen beizubehalten, wobei einer eigens für die partielle Vertrauenswürdigkeit vorgesehen\/als Sandboxing\-Lösung bereitgestellt wird.  
  
## XAML\-Namespaces und Assemblyvertrauenswürdigkeit  
 Die grundlegende nicht qualifizierte Syntax und die Definition zur Auslegung einer benutzerdefinierten XAML\-Namespace\-Zuordnung zu einer Assembly durch XAML unterscheidet nicht zwischen einer vertrauenswürdigen und nicht vertrauenswürdigen Assembly, die in die Anwendungsdomäne geladen wird.  Daher ist es für eine nicht vertrauenswürdige Assembly technisch möglich, die vorgesehene XAML\-Namespace\-Zuordnung einer vertrauenswürdigen Assembly vorzutäuschen \(Spoofing\) und die deklarierten Objekt\- und Eigenschafteninformationen einer XAML\-Quelle zu erfassen.  Wenn Sie über Sicherheitsanforderungen verfügen, um diese Situation zu vermeiden, sollte die beabsichtigte XAML\-Namespace\-Zuordnung mit einem der folgenden Verfahren vorgenommen werden:  
  
-   Verwenden Sie einen vollständig qualifizierten Assemblynamen mit starkem Namen in jeder durch die XAML der Anwendung vorgenommenen XAML\-Namespace\-Zuordnung.  
  
-   Beschränken Sie die Assemblyzuordnung auf einen festen Satz von Verweisassemblys, indem Sie einen bestimmten <xref:System.Xaml.XamlSchemaContext> für die XAML\-Reader und XAML\-Objektwriter erstellen.  Weitere Informationen finden Sie unter <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.  
  
## XAML\-Typzuordnung und Typsystemzugriff  
 XAML unterstützt ein eigenes Typsystem, das in vielerlei Hinsicht den Verfahren zum Implementieren des grundlegenden CLR\-Typsystems durch CLR gleichgeordnet ist.  Für bestimmte Aspekte des Typbewusstseins, wenn Sie Entscheidungen über die Vertrauenswürdigkeit zu einem Typ anhand der Typinformationen treffen, sollten Sie jedoch auf die Typinformationen in den CLR\-Unterstützungstypen zurückgreifen.  Dies liegt daran, dass einige der spezifischen Berichtsfunktionen des XAML\-Typsystems als virtuelle Methoden offen gelassen werden und somit nicht vollständig der Kontrolle der ursprünglichen .NET Framework\-XAML\-Dienstimplementierungen unterliegen.  Diese Erweiterbarkeitspunkte sind vorhanden, da das XAML\-Typsystem erweiterbar ist. Sie sollen eine Entsprechung zwischen der Erweiterbarkeit von XAML selbst sowie den möglichen alternativen Strategien zur Typzuordnung und der CLR\-gestützten Standardimplementierung und dem XAML\-Standardschemakontext ermöglichen.  Weitere Informationen finden Sie in den besonderen Hinweisen zu einigen der Eigenschaften von <xref:System.Xaml.XamlType> und <xref:System.Xaml.XamlMember>.  
  
## Siehe auch  
 <xref:System.Xaml.Permissions.XamlAccessLevel>