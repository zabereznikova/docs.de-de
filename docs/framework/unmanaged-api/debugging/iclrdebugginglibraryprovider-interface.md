---
title: ICLRDebuggingLibraryProvider-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
ms.openlocfilehash: 77c2011ce677d1bd2823d47740782f48151b408a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860281"
---
# <a name="iclrdebugginglibraryprovider-interface"></a>ICLRDebuggingLibraryProvider-Schnittstelle
Schließt die [Methode der ProvideLibrary-Methode](iclrdebugginglibraryprovider-providelibrary-method.md) ein, die eine Bibliotheks Anbieter-Rückruf Schnittstelle abruft, die es ermöglicht, Common Language Runtime versionsspezifische Debugbibliotheken bei Bedarf zu finden und zu laden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ProvideLibrary-Methode](iclrdebugginglibraryprovider-providelibrary-method.md)|Ermöglicht dem Debugger, ein Handle für ein Modul bereitzustellen, das zum Laden einer Debugbibliothek verwendet werden kann.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
