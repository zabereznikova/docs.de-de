---
title: Modellieren und Zuordnen
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: e70411bb9c9797ee348aeef055c9af20ea092ae3
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450595"
---
# <a name="modeling-and-mapping"></a>Modellieren und Zuordnen
Im Entity Framework können Sie das konzeptionelle Modell, das Speichermodell und die Zuordnung zwischen den beiden in der Weise definieren, die für Ihre Anwendung am besten geeignet ist. Mit den Entity Data Model-Tools in Visual Studio können Sie einen erstellen. die [EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) aus einer Datenbank oder einem grafischen Modell und aktualisiert diese Datei dann, wenn sich die Datenbank oder das Modell ändert.  
  
 Ab Entity Framework 4.1 können Sie ein Modell anhand der Code First-Entwicklung auch programmgesteuert erstellen. Es gibt zwei verschiedene Szenarien für die Code First-Entwicklung. In beiden Fällen definiert der Entwickler ein Modell, indem er .NET Framework-Klassendefinitionen codiert und dann optional zusätzliche Zuordnungen oder Konfigurationen mithilfe von Datenanmerkungen oder der Fluent-API angibt.  
  
 Weitere Informationen finden Sie unter [Erstellen eines Modells](/ef/ef6/modeling/).  
  
 Sie können auch den EDM-Generator verwenden, der in der .NET Framework enthalten ist. EdmGen.exe generiert die CSDL-, SSDL- und MSL-Dateien aus einer vorhandenen Datenquelle. Sie können Modell- und Zuordnungsinhalte auch manuell erstellen. Weitere Informationen finden Sie unter [EDM Generator (EdmGen. exe)](edm-generator-edmgen-exe.md).
