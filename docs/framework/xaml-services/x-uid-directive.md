---
title: "x:Uid Directive | Microsoft Docs"
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
  - "XAML [XAML Services], localizable content attribute"
  - "XAML [XAML Services], x:Uid attribute"
  - "x:Uid attribute [XAML Services]"
  - "Uid attribute [XAML Services]"
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
caps.latest.revision: 12
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 12
---
# x:Uid Directive
Stellt einen eindeutigen Bezeichner für Markupelemente bereit.  In vielen Szenarien wird dieser eindeutige Bezeichner von XAML\-Lokalisierungsprozessen und Tools verwendet.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object x:Uid="identifier"... />  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`identifier`|Eine manuell erstellte oder automatisch generierte Zeichenfolge, die in einer Datei eindeutig sein soll, wenn sie von einem `x:Uid`\-Consumer interpretiert wird.|  
  
## Hinweise  
 In \[MS\-XAML\] ist `x:Uid` als Direktive definiert.  Weitere Informationen finden Sie unter [b\[MS\-XAML\] Abschnitt 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 ,`x:Uid` unterscheidet sich von `x:Name` aufgrund des genannten XAML\-Lokalisierungsszenarios, und, damit die zur Lokalisierung verwendeten Bezeichner keine Abhängigkeiten von den Programmiermodellauswirkungen von `x:Name` haben.  Auch wird `x:Name` von einem XAML\-Namescope regiert, wohingegen `x:Uid` von keinem durch XAML\-Sprache definierten Konzept der Eindeutigkeitserzwingung regiert wird.  XAML\-Prozessoren im allgemeinen Sinn \(also Prozessoren, die nicht Teil des Lokalisierungsprozesses sind\) sind nicht dafür gedacht, die Eindeutigkeit von `x:Uid`\-Werten durchzusetzen.  Diese Verantwortung versteht sich beim Absender der Werte.  Die Eindeutigkeit von `x:Uid`\-Werten innerhalb einer einzelnen XAML\-Quelle wird von Consumern der Werte erwartet, also zum Beispiel von dedizierten Globalisierungsprozessen oder \-tools.  Das typische Eindeutigkeitsmodell ist, dass `x:Uid`\-Werte innerhalb einer XML\-codierten Datei, die XAML darstellt, eindeutig sind.  
  
 Tools, die bedeutendes Wissen eines bestimmten XAML\-Schemas haben, können `x:Uid` nur für wahre lokalisierbare Zeichenfolgen übernehmen statt für alle Fälle, in denen ein Textzeichenfolgenwert in Markup gefunden wird.  
  
 Frameworks können in ihrem Objektmodell eine bestimmte Eigenschaft als Alias für `x:Uid` festlegen, indem das Attributs <xref:System.Windows.Markup.UidPropertyAttribute> für den definierenden Typ übernommen wird.  Wenn ein Framework eine bestimmte Eigenschaft angibt, ist es nicht zulässig, `x:Uid` und den mit einem Alias versehenen Member auf demselben Objekt anzugeben.  Wenn `x:Uid` und der mit einem Alias versehene Member angegeben werden, löst die API der .NET Framework\-XAML\-Dienste in der Regel <xref:System.Xaml.XamlDuplicateMemberException> für diesen Fall aus.  
  
## Hinweise zur WPF\-Verwendung  
 Weitere Informationen zur Rolle von `x:Uid` in WPF\-Lokalisierungsprozess und der BAML\-Form von XAML, finden Sie unter [Globalisierung für WPF](../../../ocs/framework/wpf/advanced/globalization-for-wpf.md) oder <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## Siehe auch  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>   
 <xref:Microsoft.Build.Tasks.Windows.UidManager>   
 [Globalisierung für WPF](../../../ocs/framework/wpf/advanced/globalization-for-wpf.md)