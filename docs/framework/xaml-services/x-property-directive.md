---
title: x:Property-Anweisung
ms.date: 03/30/2017
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
ms.openlocfilehash: 7624014e0cd9ddd47cc84ee9686a6f11c27d1843
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053928"
---
# <a name="xproperty-directive"></a>x:Property-Anweisung
Deklariert eine XAML-Eigenschaft in Markup.  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```xaml  
<object x:Class="className">  
  <x:Members>  
    <x:Property Name="propertyName" Type="propertyType"/>  
    additionalProperties  
  </x:Members>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`className`|Der Name der Sicherungsklasse oder partiellen Klasse für die XAML-Produktion.|  
|`propertyName`|Der Membername der Eigenschaft, die definiert wird.|  
|`propertyType`|Der Typname (oder eine andere Zeichenfolgenform, frameworkspezifisch), der den Typ dieser Eigenschaft angibt.|  
  
## <a name="remarks"></a>Hinweise  
 In der .NET Framework-Implementierung der XAML-Dienste hat `x:Property` keine direkte Typunterstützung, wird jedoch durch die <xref:System.Windows.Markup.PropertyDefinition>-Klasse unterstützt. In einem XAML-Knotenstream wird ein `x:Property`-Element als ein Member namens `Property` aus dem XAML-Namespace der XAML-Sprache dargestellt. Der Member `Property` enthält Attribute gemäß Deklaration durch Markup.  
  
 Die Bedeutungen von `Name` und `Type` werden nicht auf der Ebene der .NET Framework-XAML-Dienste zugewiesen. Sie sind im ursprünglichen XAML-Knotenstream als Zeichenfolgenwerte gespeichert, um später gemäß den Regeln interpretiert zu werden, die möglicherweise von bestimmten Frameworks erzwungen werden. Die Bedeutung kann, je nach Implementierung, an der Bedeutung eines XAML-Namens oder eines XAML-Typs ausgerichtet werden oder kann nur in einem Unterstützungstypsystem gültig sein.  
  
 Damit eine praktische Verwendung von `x:Members` als Mittel zum Angeben von Memberdefinitionen in Markup unterstützt wird, müssen die Member einer Klasse zugeordnet sein, die geändert werden kann. Das beabsichtigte Modell besteht darin, dass `x:Members` als ein Member eines Typs vorhanden ist, der eine `x:Class` angibt. Der Mechanismus zum Zuordnen von Typen und Membern oder zum Erstellen von dynamischen Memberdefinitionen wird jedoch auf der Ebene der .NET Framework-XAML-Dienste nicht unterstützt. Dies wird von einzelnen Frameworks übernommen, die Anwendungsmodelle haben, die Memberdefinitionen von XAML unterstützen. In der Regel sind, damit dieses Feature unterstützt wird, MSBUILD-Buildvorgänge erforderlich, die XAML als Markup kompilieren und es als CodeBehind integrieren oder reine Von-XAML-Assemblys generieren.  
  
## <a name="xproperty-for-windows-workflow-foundation"></a>x:Property für Windows Workflow Foundation  
 Für Windows Workflow Foundation definiert `x:Property` die Member einer benutzerdefinierten Aktivität, die vollständig in XAML erstellt ist, oder XAML-definierte dynamische Member für einen Aktivitäts-Designer mit CodeBehind. `x:Class` muss auch für das Stammelement der XAML-Produktion angegeben werden. Dies ist keine Anforderung auf der Ebene der .NET Framework-XAML-Dienste, wird jedoch eine Anforderung, wenn die XAML-Produktion von MSBUILD-Buildvorgängen geladen wird, die benutzerdefinierte Aktivitäten und Windows Workflow Foundation-XAML im Allgemeinen unterstützen. Windows Workflow Foundation verwendet nicht den reinen XAML-Typnamen als beabsichtigten Wert für das `x:Property` `Type` Attribut, sondern verwendet stattdessen eine Konvention, die hier nicht dokumentiert ist. Weitere Informationen finden Sie unter [DynamicActivity-Erstellung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).
