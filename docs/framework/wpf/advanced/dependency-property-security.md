---
title: "Sicherheit von Abh&#228;ngigkeitseigenschaften | Microsoft Docs"
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
  - "Abhängigkeitseigenschaften, Zugriff"
  - "Abhängigkeitseigenschaften, Sicherheit"
  - "Sicherheit, Abhängigkeitseigenschaften"
  - "Sicherheit, Wrapper"
  - "Überprüfung, Abhängigkeitseigenschaften"
  - "Wrapper, Zugriff"
  - "Wrapper, Sicherheit"
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Sicherheit von Abh&#228;ngigkeitseigenschaften
Abhängigkeitseigenschaften sollten in der Regel als öffentliche Eigenschaften angesehen werden.  Die Beschaffenheit des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Eigenschaftensystems verhindert, dass für den Wert einer Abhängigkeitseigenschaft Sicherheitsgarantien aufgestellt werden.  
  
   
  
<a name="AccessSecurity"></a>   
## Zugriff und Sicherheit von Wrappern und Abhängigkeitseigenschaften  
 Normalerweise werden Abhängigkeitseigenschaften zusammen mit [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Wrappereigenschaften implementiert, die das Abrufen und Festlegen der Eigenschaft über eine Instanz vereinfachen.  Bei den Wrappern handelt es sich jedoch lediglich um Hilfsmethoden, die die zugrunde liegenden statischen Aufrufe <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> implementieren, die beim Interagieren mit Abhängigkeitseigenschaften verwendet werden.  Sie können es sich auch so vorstellen, dass die Eigenschaften als [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Eigenschaften offengelegt werden, die von einer Abhängigkeitseigenschaft unterstützt werden, anstatt von einem privaten Feld.  Sicherheitsmechanismen, die auf Wrapper angewendet werden, gelten nicht parallel zum Verhalten des Eigenschaftensystems und zum Zugriff auf die zugrunde liegende Abhängigkeitseigenschaft.  Das Versehen des Wrappers mit einer Sicherheitsforderung verhindert lediglich die Verwendung der Hilfsmethode, jedoch keine Aufrufe an <xref:System.Windows.DependencyObject.GetValue%2A> oder <xref:System.Windows.DependencyObject.SetValue%2A>.  Auch das Versehen der Wrapper mit geschützten oder privaten Zugriffsebenen bietet keine effektive Sicherheit.  
  
 Wenn Sie Ihre eigenen Abhängigkeitseigenschaften schreiben, sollten Sie die Wrapper und das <xref:System.Windows.DependencyProperty>\-Bezeichnerfeld als öffentliche Member deklarieren, damit Aufrufer keine irreführenden Informationen zur geltenden Zugriffsebene der Eigenschaft erhalten \(da als Speicher eine Abhängigkeitseigenschaft implementiert ist\).  
  
 Für eine benutzerdefinierte Abhängigkeitseigenschaft können Sie Ihre Eigenschaft als schreibgeschützte Abhängigkeitseigenschaft registrieren. So können Sie auf effektive Weise verhindern, dass eine Eigenschaft von beliebigen Elementen festgelegt wird, die über keinen Verweis auf den <xref:System.Windows.DependencyPropertyKey> für die jeweilige Eigenschaft verfügen.  Weitere Informationen finden Sie unter [Schreibgeschützte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).  
  
> [!NOTE]
>  Das Deklarieren eines <xref:System.Windows.DependencyProperty>\-Bezeichnerfelds ist nicht unzulässig, und Sie können diesen Ansatz verwenden, um dazu beizutragen, den sofort offengelegten Namespace einer benutzerdefinierten Klasse zu reduzieren. Eine Eigenschaft dieser Art ist jedoch nicht in gleichem Maße als "privat" anzusehen wie die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Sprachdefinitionen, die diese Zugriffsebene definieren. Die Gründe dafür sind im nächsten Abschnitt beschrieben.  
  
<a name="PropertySystemExposure"></a>   
## Eigenschaftensystem\-Offenlegung von Abhängigkeitseigenschaften  
 Es ist im Allgemeinen nicht ratsam und ggf. irreführend, für eine <xref:System.Windows.DependencyProperty> eine andere Zugriffsebene als "öffentlich" zu deklarieren.  Diese Zugriffsebeneneinstellung verhindert lediglich, dass von der deklarierenden Klasse aus ein Verweis auf die Instanz eingerichtet wird.  Es gibt jedoch mehrere Aspekte des Eigenschaftensystems, die eine <xref:System.Windows.DependencyProperty> als Mittel zum Identifizieren einer bestimmten Eigenschaft zurückgeben, wie diese in der Instanz einer Klasse oder abgeleiteten Klasse vorhanden ist. Dieser Bezeichner kann auch dann in einem <xref:System.Windows.DependencyObject.SetValue%2A>\-Aufruf verwendet werden, wenn der ursprüngliche statische Bezeichner als nicht öffentlich deklariert wird.  Virtuelle <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>\-Methoden erhalten Informationen zu vorhandenen Abhängigkeitseigenschaften, deren Wert sich geändert hat.  Außerdem gibt die <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A>\-Methode Bezeichner für alle Eigenschaften von Instanzen mit einem lokal festgelegten Wert zurück.  
  
### Validierung und Sicherheit  
 Das Anwenden einer Forderung auf einen <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> und die Erwartung, dass eine fehlgeschlagene Validierung eines Forderungsfehlschlags verhindert, dass eine Eigenschaft festgelegt wird, ist kein geeigneter Sicherheitsmechanismus.  Die Ungültigkeit von festgelegten Werten per <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> kann auch von böswilligen Aufrufern erzwungen werden, wenn diese Aufrufer sich innerhalb der Anwendungsdomäne befinden.  
  
## Siehe auch  
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)