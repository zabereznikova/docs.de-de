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
ms.openlocfilehash: 1986d5f91a3dcfa31a43f729ee1f50129e083f5f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501741"
---
# <a name="isymunmanagedencupdate-interface"></a>ISymUnmanagedENCUpdate-Schnittstelle
Stellt Funktionen für die Funktion "Bearbeiten und Fortfahren" bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetLocalVariableCount-Methode](isymunmanagedencupdate-getlocalvariablecount-method.md)|Ruft die Anzahl der lokalen Variablen ab.|  
|[GetLocalVariables-Methode](isymunmanagedencupdate-getlocalvariables-method.md)|Ruft die lokalen Variablen ab.|  
|[InitializeForEnc-Methode](isymunmanagedencupdate-initializeforenc-method.md)|Ermöglicht das Berechnen von Methoden Begrenzungen vor dem ersten Aufrufen der [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) -Methode.|  
|[UpdateMethodLines-Methode](isymunmanagedencupdate-updatemethodlines-method.md)|Ermöglicht das Aktualisieren der Zeilen Informationen für eine Methode, die nicht erneut kompiliert wurde, deren Zeilen jedoch unabhängig voneinander verschoben wurden. Ein Delta für jede Anweisung ist zulässig.|  
|[UpdateSymbolStore2-Methode](isymunmanagedencupdate-updatesymbolstore2-method.md)|Ermöglicht einem Compiler das Weglassen von Funktionen, die nicht aus dem Datenstrom der Programmdatenbank (PDB) geändert wurden, vorausgesetzt, die Zeilen Informationen erfüllen die Anforderungen. Die richtigen Zeilen Informationen können mit den alten PDB-Zeilen Informationen und einem Delta für alle Zeilen in der Funktion bestimmt werden.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen:

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
