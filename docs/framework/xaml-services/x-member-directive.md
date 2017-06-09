---
title: "x:Member Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
caps.latest.revision: 5
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 5
---
# x:Member Directive
Deklariert einen XAML\-Member im Markup.  
  
## Verwendung von XAML\-Objektelementen  
  
```  
  
<object x:Class="className">  
  <x:Members>  
    <x:Member Name="propertyName"/>  
    additionalMembers  
  </x:Members>  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`className`|Der Name der Sicherungsklasse oder partiellen Klasse für die XAML\-Produktion.|  
|`memberName`|Der Membername der Eigenschaft, die definiert wird.|  
  
## Hinweise  
 In der .NET Framework\-Implementierung der XAML\-Dienste  hat `x:Member` keine direkte Typunterstützung, wird jedoch durch die <xref:System.Windows.Markup.MemberDefinition>\-Klasse unterstützt.  In einem XAML\-Knotenstream wird ein `x:Member`\-Element als ein Member namens `Member` aus dem XAML\-Namespace der XAML\-Sprache dargestellt.  Der Member `Member` enthält Attribute gemäß Deklaration durch Markup.  
  
 Die Bedeutungen von `Name` und `Type` werden nicht auf der Ebene der .NET Framework\-XAML\-Dienste zugewiesen.  Sie sind im ursprünglichen XAML\-Knotenstream als Zeichenfolgenwerte gespeichert, um später gemäß den Regeln interpretiert zu werden, die möglicherweise von bestimmten Frameworks erzwungen werden.  Die Bedeutung kann, je nach Implementierung, an der Bedeutung eines XAML\-Namens oder eines XAML\-Typs ausgerichtet werden oder kann nur in einem Unterstützungstypsystem gültig sein.  
  
 Damit eine praktische Verwendung von `x:Members` als Mittel zum Angeben von Memberdefinitionen in Markup unterstützt wird, müssen die Member einer Klasse zugeordnet sein, die geändert werden kann.  Das beabsichtigte Modell besteht darin, dass `x:Members` als ein Member eines Typs vorhanden ist, der eine `x:Class` angibt.  Der Mechanismus zum Zuordnen von Typen und Membern oder zum Erstellen von dynamischen Memberdefinitionen wird jedoch auf der Ebene der .NET Framework\-XAML\-Dienste nicht unterstützt.  Dies wird von einzelnen Frameworks übernommen, die Anwendungsmodelle haben, die Memberdefinitionen von XAML unterstützen.  In der Regel sind, damit dieses Feature unterstützt wird, MSBUILD\-Buildvorgänge erforderlich, die XAML als Markup kompilieren und es als CodeBehind integrieren oder reine Von\-XAML\-Assemblys generieren.  
  
## x:Property für Windows Workflow Foundation  
 Für Windows Workflow Foundation definiert `x:Property` die Member einer benutzerdefinierten Aktivität, die vollständig in XAML erstellt ist, oder XAML\-definierte dynamische Member für einen Aktivitäts\-Designer mit CodeBehind.  `x:Class` muss auch für das Stammelement der XAML\-Produktion angegeben werden.  Dies ist keine Anforderung auf der Ebene der .NET Framework\-XAML\-Dienste, wird jedoch eine Anforderung, wenn die XAML\-Produktion von MSBUILD\-Buildvorgängen geladen wird, die benutzerdefinierte Aktivitäten und Windows Workflow Foundation\-XAML im Allgemeinen unterstützen.  Windows Workflow Foundation verwendet nicht den reinen XAML\-Typnamen als beabsichtigten Wert für das `x:Property` `Type`\-Attribut, sondern verwendet stattdessen eine Konvention, die hier nicht dokumentiert ist.  Weitere Informationen finden Sie unter [DynamicActivity\-Erstellung](http://msdn.microsoft.com/library/dd807392.aspx).