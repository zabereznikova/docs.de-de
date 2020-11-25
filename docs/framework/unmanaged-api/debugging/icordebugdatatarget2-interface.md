---
title: ICorDebugDataTarget2-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: aa1db39b564b987fb8d0f79d529f5af59b7e4c02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713748"
---
# <a name="icordebugdatatarget2-interface"></a>ICorDebugDataTarget2-Schnittstelle

Erweitert logisch die [ICorDebug DataTarget](icordebugdatatarget-interface.md)-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CreateVirtualUnwinder-Methode](icordebugdatatarget2-createvirtualunwinder-method.md)|Erstellt einen neuen Stapelentlader, der mit dem Entladen bei einem Anfangskontext beginnt (welcher nicht unbedingt das Blatt eines Threads ist).|  
|[EnumerateThreadIDs-Methode](icordebugdatatarget2-enumeratethreadids-method.md)|Gibt eine Liste der aktiven Thread-IDs aus.|  
|[GetImageFromPointer-Methode](icordebugdatatarget2-getimagefrompointer-method.md)|Gibt die Basisadresse des Moduls und die Größe von einer Adresse in diesem Modul aus.|  
|[GetImageLocation-Methode](icordebugdatatarget2-getimagelocation-method.md)|Gibt den Pfad eines Moduls aus der Basisadresse des Moduls zurück.|  
|[GetSymbolProviderForImage-Methode](icordebugdatatarget2-getsymbolproviderforimage-method.md)|Gibt anhand der Basisadresse des Moduls den Symbol-Anbieter für ein Modul aus.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
