---
title: "x:Shared Attribute | Microsoft Docs"
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
  - "XAML [XAML Services], x:Shared attribute"
  - "x:Shared attribute [XAML Services]"
  - "Shared attribute in XAML [XAML Services]"
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
caps.latest.revision: 16
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 16
---
# x:Shared Attribute
Wenn dieses Attribut auf `false` gesetzt ist, ändert es das WPF\-Ressourcenabrufverhalten so, dass bei Anforderungen einer Attributressource für jede Anforderung jeweils eine neue Instanz erstellt wird, anstatt eine Instanz für alle Anforderungen zu verwenden.  
  
## Verwendung von XAML\-Attributen  
  
```  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## Hinweise  
 `x:Shared` wird in den XAML\-Sprachnamenbereich zugeordnet und wird von .NET Framework\-XAML\-Diensten und seinen XAML\-Readern als gültiges XAML\-Sprachelement erkannt.  Die angegebenen Funktionen von `x:Shared` sind jedoch nur für WPF\-Anwendungen und den WPF\-XAML\-Parser relevant.  In WPF ist `x:Shared` als Attribut nur nützlich, wenn es auf ein Objekt angewendet wird, das innerhalb eines WPF <xref:System.Windows.ResourceDictionary> vorhanden ist.  Andere Verwendungen lösen keine Analyseausnahmen oder andere Fehler aus, aber sie haben keine Auswirkungen.  
  
 Die Bedeutung von `x:Shared` wird nicht in der XAML\-Sprachspezifikation angegeben.  Andere XAML\-Implementierungen, z. B. die, die auf .NET Framework\-XAML\-Diensten aufbauen, stellen nicht notwendigerweise Ressourcenfreigabeunterstützung bereit.  Solche XAML\-Implementierungen könnten ähnliches Verhalten im unterstützenden Framework bereitstellen, das auch `x:Shared`\-Werte verwendete.  
  
 In WPF lautet die standardmäßige `x:Shared`\-Bedingung von Ressourcen `true`.  Diese Bedingung bedeutet, dass jede Ressourcenanforderung immer dieselbe Instanz zurückgibt.  
  
 Beim Ändern eines Objekts, das über eine Ressourcen\-API, wie z.B. <xref:System.Windows.FrameworkElement.FindResource%2A> zurückgegeben wird, oder beim direkten Ändern eines Objekts in einem <xref:System.Windows.ResourceDictionary> wird die ursprüngliche Ressource geändert.  Wenn es sich bei den Verweisen auf diese Ressource um dynamische Verweise gehandelt hat, erhalten die Consumer dieser Ressource die geänderte Ressource.  
  
 \(Wenn es sich bei den Verweisen auf die Ressource um statische Ressourcenverweise gehandelt hat, sind Änderungen der Ressource nach dem [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]\-Verarbeitungszeitraum irrelevant.  Weitere Informationen zu den Unterschieden zwischen statischen und dynamischen Ressourcenverweisen finden Sie unter [XAML\-Ressourcen](../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Das explizite Angeben von `x:Shared="true"` erfolgt selten, weil dies bereits die Standardeinstellung ist.  Es gibt keine direkte Codeentsprechung für `x:Shared` im WPF\-Objektmodell. Es kann nur in einer XAML\-Verwendung angegeben werden und muss entweder durch das Standard\-WPF\-Verhalten oder in einem Zwischen\-XAML\-Knotenstream auf dem Ladepfad verarbeitet werden, wenn es mit .NET Framework\-XAML\-Diensten und seinen XAML\-Readern verarbeitet wird.  
  
 Ein Szenario für `x:Shared="false"` ist, wenn Sie eine abgeleitete Klasse von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> als Ressource definieren und dann die Elementressource in ein Inhaltsmodell einfügen.  Mithilfe von `x:Shared="false"` kann eine Elementressource mehrfach in eine Auflistung eingefügt werden \(z. B. in eine <xref:System.Windows.Controls.UIElementCollection>\).  Ohne `x:Shared="false"` ist dies nicht gültig, weil die Auflistung die Eindeutigkeit ihres Inhalts erzwingt.  Allerdings erstellt das `x:Shared="false"`\-Verhalten eine weitere identische Instanz der Ressource, statt die gleiche Instanz zurückzugeben.  
  
 Ein anderes Szenario für `x:Shared="false"` ist, wenn Sie eine <xref:System.Windows.Freezable>\-Ressource für Animationswerte verwenden, die Ressource jedoch individuell pro Animation ändern möchten.  
  
 Bei der Zeichenfolgenbehandlung von `false` wird die Groß\-\/Kleinschreibung nicht berücksichtigt.  
  
 In WPF ist `x:Shared` nur unter den folgenden Bedingungen gültig:  
  
-   Das <xref:System.Windows.ResourceDictionary>, das die Elemente mit `x:Shared` enthält, muss kompiliert sein.  Das <xref:System.Windows.ResourceDictionary> darf sich nicht innerhalb von losen XAML\-Daten befinden oder für Designs verwendet werden.  
  
-   Das <xref:System.Windows.ResourceDictionary>, das die Elemente enthält, darf nicht in ein anderes <xref:System.Windows.ResourceDictionary> geschachtelt sein.  Sie können `x:Shared` z. B. nicht für Elemente in einem <xref:System.Windows.ResourceDictionary> verwenden, das einen <xref:System.Windows.Style> aufweist, bei dem es sich bereits um ein <xref:System.Windows.ResourceDictionary>\-Element handelt.  
  
## Siehe auch  
 <xref:System.Windows.ResourceDictionary>   
 [XAML\-Ressourcen](../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Basiselemente](../../../docs/framework/wpf/advanced/base-elements.md)