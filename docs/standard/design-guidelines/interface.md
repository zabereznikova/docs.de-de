---
title: Schnittstellenentwurf
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8636653ca856693961cbfc73e9170410ed2cd361
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="interface-design"></a>Schnittstellenentwurf
Obwohl die meisten APIs am besten mithilfe von Klassen und Strukturen modelliert werden, stehen die Fälle, in denen Schnittstellen sind besser geeignet oder die einzige Option.  
  
 Die CLR unterstützt keine mehrfachvererbung (d. h., CLR-Klassen aus mehr als einer Basisklasse erben können nicht), jedoch Typen eine oder mehrere Schnittstellen zusätzlich zu den von einer Basisklasse erben. Daher sind Schnittstellen häufig verwendet, um die Auswirkung der mehrfachvererbung zu erzielen. Beispielsweise <xref:System.IDisposable> ist eine Schnittstelle, über Typen zur Unterstützung Disposability unabhängig von anderen Vererbungshierarchie-befindet, in dem sie teilnehmen möchten.  
  
 Das andere Szenario, in welche, das definieren eine Schnittstelle geeignet ist, ist bei der Erstellung einer gemeinsamen Schnittstelle, die von mehreren Typen, z. B. einige Werttypen unterstützt werden kann. Werttypen nicht außer von Typen erben <xref:System.ValueType>, jedoch Schnittstellen implementieren, also über eine Schnittstelle ist die einzige Option, um einen allgemeinen Basistyp bereitzustellen.  
  
 **Führen Sie ✓** definieren Sie eine Schnittstelle aus, wenn Sie einige gemeinsame-API benötigen, von einem Satz von Typen unterstützt werden müssen, die Werttypen enthält.  
  
 **✓ GGF.** zum Definieren einer Schnittstelle, wenn Sie seine Funktionalität auf Typen zu unterstützen, die bereits von einem anderen Typ erben müssen.  
  
 **X vermeiden** Markerschnittstellen (ohne Member) verwenden.  
  
 Wenn Sie eine Klasse mit einem bestimmten Merkmal (Marker) markieren müssen, verwenden Sie in der Regel eine Schnittstelle, anstatt ein benutzerdefiniertes Attribut.  
  
 **Führen Sie ✓** Geben Sie mindestens einen Typ, die Implementierung einer Schnittstelle.  
  
 Dies So überprüfen Sie den Entwurf der Schnittstelle. Beispielsweise <xref:System.Collections.Generic.List%601> ist eine Implementierung der <xref:System.Collections.Generic.IList%601> Schnittstelle.  
  
 **Führen Sie ✓** Geben Sie mindestens eine API, die jede Schnittstelle nutzt Sie definieren (eine Methode, die die Schnittstelle als Parameter oder einer Eigenschaft annimmt, die als Schnittstelle eingegeben wird).  
  
 Dies So überprüfen Sie den Schnittstellenentwurf. Beispielsweise <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> nutzt die <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> Schnittstelle.  
  
 **X nicht** Hinzufügen von Mitgliedern zu einer Schnittstelle, die zuvor gesendet wurde.  
  
 Auf diese Weise wird die Implementierung der Schnittstelle unterbrochen. Sie sollten eine neue Schnittstelle erstellen, um Versionsprobleme zu vermeiden.  
  
 Außer den in der folgenden Richtlinien beschriebenen Situationen, in der Regel Klassen statt Schnittstellen Entscheidung können Sie in verwalteten Codebibliotheken wiederverwendbare entwerfen.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
