---
title: Modellieren und Zuordnen
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 133539ab1b6d6f2f0ab3f8deed5b22240c2bb07e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854390"
---
# <a name="modeling-and-mapping"></a>Modellieren und Zuordnen
Im Entity Framework können Sie das konzeptionelle Modell, das Speichermodell und die Zuordnung zwischen den beiden in der Weise definieren, die für Ihre Anwendung am besten geeignet ist. Mit den Entity Data Model-Tools in Visual Studio können Sie einen erstellen. die [EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) aus einer Datenbank oder einem grafischen Modell und aktualisiert diese Datei dann, wenn sich die Datenbank oder das Modell ändert.  
  
 Ab Entity Framework 4.1 können Sie ein Modell anhand der Code First-Entwicklung auch programmgesteuert erstellen. Es gibt zwei verschiedene Szenarien für die Code First-Entwicklung. In beiden Fällen definiert der Entwickler ein Modell, indem er .NET Framework-Klassendefinitionen codiert und dann optional zusätzliche Zuordnungen oder Konfigurationen mithilfe von Datenanmerkungen oder der Fluent-API angibt.  
  
 Weitere Informationen finden Sie unter [Erstellen und Mapping eines konzeptionellen Modells](https://go.microsoft.com/fwlink/?LinkId=235016).  
  
 Sie können auch den EDM-Generator verwenden, der in der .NET Framework enthalten ist. EdmGen.exe generiert die CSDL-, SSDL- und MSL-Dateien aus einer vorhandenen Datenquelle. Sie können Modell- und Zuordnungsinhalte auch manuell erstellen. Weitere Informationen finden Sie unter [EDM Generator (EdmGen. exe)](edm-generator-edmgen-exe.md).
