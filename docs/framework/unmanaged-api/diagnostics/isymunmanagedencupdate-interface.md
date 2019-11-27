---
title: ISymUnmanagedENCUpdate-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: f3305a7bb003fc50f772f1100f8a17d385e4d5fc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449008"
---
# <a name="isymunmanagedencupdate-interface"></a>ISymUnmanagedENCUpdate-Schnittstelle
Stellt Funktionen für die Funktion "Bearbeiten und Fortfahren" bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetLocalVariableCount-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|Ruft die Anzahl der lokalen Variablen ab.|  
|[GetLocalVariables-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|Ruft die lokalen Variablen ab.|  
|[InitializeForEnc-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|Ermöglicht das Berechnen von Methoden Begrenzungen vor dem ersten Aufrufen der [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) -Methode.|  
|[UpdateMethodLines-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|Ermöglicht das Aktualisieren der Zeilen Informationen für eine Methode, die nicht erneut kompiliert wurde, deren Zeilen jedoch unabhängig voneinander verschoben wurden. Ein Delta für jede Anweisung ist zulässig.|  
|[UpdateSymbolStore2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|Ermöglicht einem Compiler das Weglassen von Funktionen, die nicht aus dem Datenstrom der Programmdatenbank (PDB) geändert wurden, vorausgesetzt, die Zeilen Informationen erfüllen die Anforderungen. Die richtigen Zeilen Informationen können mit den alten PDB-Zeilen Informationen und einem Delta für alle Zeilen in der Funktion bestimmt werden.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
