---
title: "x:Members Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
caps.latest.revision: 5
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 5
---
# x:Members Directive
Enthält einen Satz von Membern, die im Markup definiert sind, die für die x:Class des übergeordneten Elements gelten.  
  
## Verwendung von XAML\-Attributen  
  
```  
  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`className`|Name der Sicherungsklasse oder partiellen Klasse für die XAML\-Produktion.  Siehe Hinweise.|  
|`oneOrMoreMembers`|Ein oder mehrere Objektelemente, die Memberdefinitionen darstellen.  Normalerweise sind dies `x:Property`\-Objektelemente.  Siehe Hinweise.|  
  
## Hinweise  
 In der Implementierung für .NET Framework\-XAML\-Dienste gibt es keine Sicherungsklasse oder zugrunde liegende Memberimplementierung für `x:Members`.  `x:Members` ist ein spezieller XAML\-Member, der als Member für jeden Typ vorhanden sein kann.  In einem XAML\-Knotenstream wird `x:Members` als `Members`\-Member aus dem XAML\-Sprachnamespace dargestellt.  Der Member `Members` enthält eine schreibgeschützte generische Liste von `Member`\-Objekten.  Im typischen Markup werden die einzelnen Member als `x:Property`\-Eigenschaftenelemente angegeben.  `x:Property` ist ein präziserer Typ speziell für Eigenschaften von Typen und kann `x:Member` zugeordnet werden.  Weitere Informationen finden Sie unter [x:Property Directive](../../../docs/framework/xaml-services/x-property-directive.md).  
  
 Um eine praktische Verwendung von `x:Members` als Mittel zum Angeben von Memberdefinitionen im Markup zu unterstützen, müssen die Member einer Klasse zugeordnet sein, die geändert werden kann.  Das gewünschte Modell besteht darin, dass `x:Members` als Member eines Typs vorhanden ist, der `x:Class` angibt.  Allerdings wird der Mechanismus zum Zuordnen von Typen und Membern oder zum Erzeugen dynamischer Memberdefinitionen auf der Ebene der .NET Framework\-XAML\-Dienste nicht unterstützt.  Dies wird von einzelnen Frameworks übernommen, die Anwendungsmodelle enthalten, die Memberdefinitionen von XAML unterstützen.  In der Regel sind MSBUILD\-Buildvorgänge, die XAML als Markup kompilieren und es als Code\-Behind integrieren oder reine FROM XAML\-Assemblys generieren, erforderlich, um diese Funktion zu unterstützen.  
  
## x:Members für Windows Workflow Foundation  
 Für Windows Workflow Foundation enthält `x:Members` die Member einer vollständig in XAML erstellten benutzerdefinierten Aktivität oder dynamische XAML\-definierte Member für einen Aktivitäts\-Designer mit Code\-Behind.  `x:Class` muss auch im Stammelement der XAML\-Produktion angegeben werden.  Dies ist keine Anforderung auf der .NET Framework\-XAML\-Dienstebene, wird jedoch eine Anforderung, wenn die XAML\-Produktion von MSBUILD\-Buildvorgängen geladen wird, die benutzerdefinierte Aktivitäten und Windows Workflow Foundation\-XAML im Allgemeinen unterstützen.  `x:Members` muss das erste untergeordnete Element im Markup des Objektelements sein, das `x:Class` deklariert.