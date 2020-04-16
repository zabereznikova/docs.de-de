---
title: x:Property-Anweisung
ms.date: 03/30/2017
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
ms.openlocfilehash: 2804ec935d0626cba9ef050f70a3266cf23bcce0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432677"
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

## <a name="remarks"></a>Bemerkungen

In .NET XAML Services-Implementierung , . hat `x:Property` keine direkte Typunterstützung, wird jedoch durch die <xref:System.Windows.Markup.PropertyDefinition>-Klasse unterstützt. In einem XAML-Knotenstream wird ein `x:Property`-Element als ein Member namens `Property` aus dem XAML-Namespace der XAML-Sprache dargestellt. Der Member `Property` enthält Attribute gemäß Deklaration durch Markup.

Die Bedeutung `Name` `Type` von und werden nicht auf .NET XAML Services-Ebene zugewiesen. Sie sind im ursprünglichen XAML-Knotenstream als Zeichenfolgenwerte gespeichert, um später gemäß den Regeln interpretiert zu werden, die möglicherweise von bestimmten Frameworks erzwungen werden. Die Bedeutung kann, je nach Implementierung, an der Bedeutung eines XAML-Namens oder eines XAML-Typs ausgerichtet werden oder kann nur in einem Unterstützungstypsystem gültig sein.

Damit eine praktische Verwendung von `x:Members` als Mittel zum Angeben von Memberdefinitionen in Markup unterstützt wird, müssen die Member einer Klasse zugeordnet sein, die geändert werden kann. Das beabsichtigte Modell besteht darin, dass `x:Members` als ein Member eines Typs vorhanden ist, der eine `x:Class` angibt. Der Mechanismus zum Zuordnen von Typen und Membern oder zum Erstellen dynamischer Memberdefinitionen wird jedoch auf .NET XAML Services-Ebene nicht unterstützt. Dies wird von einzelnen Frameworks übernommen, die Anwendungsmodelle haben, die Memberdefinitionen von XAML unterstützen. In der Regel sind, damit dieses Feature unterstützt wird, MSBUILD-Buildvorgänge erforderlich, die XAML als Markup kompilieren und es als CodeBehind integrieren oder reine Von-XAML-Assemblys generieren.

## <a name="xproperty-for-windows-workflow-foundation"></a>x:Property für Windows Workflow Foundation

Für Windows Workflow Foundation definiert `x:Property` die Member einer benutzerdefinierten Aktivität, die vollständig in XAML erstellt ist, oder XAML-definierte dynamische Member für einen Aktivitäts-Designer mit CodeBehind. `x:Class` muss auch für das Stammelement der XAML-Produktion angegeben werden. Dies ist keine Anforderung auf .NET XAML Services-Ebene, wird aber zu einer Anforderung, wenn die XAML-Produktion von den MSBUILD-Buildaktionen geladen wird, die benutzerdefinierte Aktivitäten und Windows Workflow Foundation XAML im Allgemeinen unterstützen. Windows Workflow Foundation verwendet nicht den reinen XAML-Typnamen als beabsichtigten Wert für das `x:Property` `Type` Attribut, sondern eine Konvention, die hier nicht dokumentiert ist. Weitere Informationen finden Sie unter [DynamicActivity Creation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).
