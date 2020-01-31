---
title: Profilerstellungsstrukturen
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: c3bbc66079e05abf494ad112b8aa0ac68e3c3e2f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868108"
---
# <a name="profiling-structures"></a>Profilerstellungsstrukturen
In diesem Abschnitt werden die nicht verwalteten Strukturen beschrieben, die die Profilerstellungs-API verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur](cor-prf-assembly-reference-info-structure.md)  
 Liefert der Common Language Runtime Informationen über einen Assemblyverweis, der beachtet werden muss, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.  
  
 [COR_PRF_CODE_INFO-Struktur](cor-prf-code-info-structure.md)  
 Stellt einen zusammenhängenden Block von im Speicher befindlichem systemeigenem Code dar.  
  
 [COR_PRF_EX_CLAUSE_INFO-Struktur](cor-prf-ex-clause-info-structure.md)  
 Speichert Informationen über eine bestimmte Instanz einer Ausnahmeklausel und deren zugeordneten Rahmen.  
  
 [COR_PRF_FUNCTION-Struktur](cor-prf-function-structure.md)  
 Bietet eine eindeutige Darstellung einer Funktion aus der Kombination ihrer ID mit der ID der neu kompilierten Version.  
  
 [COR_PRF_FUNCTION_ARGUMENT_INFO-Struktur](cor-prf-function-argument-info-structure.md)  
 Stellt die Argumente einer Funktion dar, in Reihenfolge von links nach rechts.  
  
 [COR_PRF_FUNCTION_ARGUMENT_RANGE-Struktur](cor-prf-function-argument-range-structure.md)  
 Stellt einen Block von Funktionsargumenten dar, die nacheinander in der Reihenfolge von links nach rechts im Arbeitsspeicher gespeichert sind.  
  
 [COR_PRF_GC_GENERATION_RANGE-Struktur](cor-prf-gc-generation-range-structure.md)  
 Beschreibt einen Bereich (d. h. einen Block) des Speichers, der einer Garbage Collection unterzogen wird.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 COR_DEBUG_IL_TO_NATIVE_MAP  
  
 COR_IL_MAP  
  
 [Übersicht über die Profilerstellung](profiling-overview.md)  
  
 [Profilerstellungsschnittstellen](profiling-interfaces.md)  
  
 [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)  
  
 [Profilerstellungsenumerationen](profiling-enumerations.md)
