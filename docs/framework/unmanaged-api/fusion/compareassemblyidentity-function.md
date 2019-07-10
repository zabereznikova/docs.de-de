---
title: CompareAssemblyIdentity-Funktion
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55d4e936c8b732e4cc4a60df8c11b37c86c4a415
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778480"
---
# <a name="compareassemblyidentity-function"></a>CompareAssemblyIdentity-Funktion
Vergleicht zwei Assemblyidentitäten aus, um festzustellen, ob sie gleich sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzAssemblyIdentity1`  
 [in] Die Text Identität der ersten Assembly im Vergleich.  
  
 `fUnified1`  
 [in] Ein boolesches Flag zur Angabe von benutzerdefinierten Vereinheitlichung für `pwzAssemblyIdentity1`.  
  
 `pwzAssemblyIdentity2`  
 [in] Die Text Identität der zweiten Assembly im Vergleich.  
  
 `fUnified2`  
 [in] Ein boolesches Flag zur Angabe von benutzerdefinierten Vereinheitlichung für `pwzAssemblyIdentity2`.  
  
 `pfEquivalent`  
 [out] Ein boolesches Flag, der angibt, ob die beiden Assemblys identisch sind.  
  
 `pResult`  
 [out] Ein [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) -Enumeration, die ausführliche Informationen über den Vergleich enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 `pfEquivalent` Gibt einen booleschen Wert, der angibt, ob die beiden Assemblys identisch sind. `pResult` Gibt einen von der `AssemblyComparisonResult` Werte und geben Sie einen ausführlicheren Grund für den Wert des `pfEquivalent`.  
  
## <a name="remarks"></a>Hinweise  
 `CompareAssemblyIdentity` überprüft, ob `pwzAssemblyIdentity1` und `pwzAssemblyIdentity2` entsprechen. `pfEquivalent` nastaven NA hodnotu `true` unter eine oder mehrere der folgenden Bedingungen:  
  
- Die zwei Assemblyidentitäten entsprechen. Für Assemblys mit starkem Namen erfordert die Äquivalenz der Assemblyname, Version, Token des öffentlichen Schlüssels und Kultur identisch sein. Für Assemblys mit einfachen Namen erfordert die Äquivalenz eine Übereinstimmung bei den Assemblynamen und Kultur.  
  
- Beide Assemblyidentitäten verweisen auf Assemblys, die auf .NET Framework ausgeführt. Diese Bedingung gibt `true` , auch wenn die Versionsnummern der Assembly nicht übereinstimmen.  
  
- Die beiden Assemblys sind nicht verwaltete Assemblys, aber `fUnified1` oder `fUnified2` wurde `true`.  
  
 Die `fUnified` Flag gibt an, dass alle Versionsnummern bis zu die Versionsnummer der Assembly mit starkem Namen entspricht, auf die Assembly mit starkem Namen berücksichtigt werden. Z. B. wenn der Wert des `pwzAssemblyIndentity1` ist "MyAssembly, Version = 3.0.0.0, Culture = Neutral, PublicKeyToken =...", und der Wert der `fUnified1` ist `true`, dies weist darauf hin, dass alle Versionen von MyAssembly, Version "0.0.0.0" bis 3.0.0.0 sein soll als gleichwertig behandelt. In diesem Fall wenn `pwzAssemblyIndentity2` bezieht sich auf der gleichen Assembly wie `pwzAssemblyIndentity1`, außer dass es auf eine niedrigere Versionsnummer wurde `pfEquivalent` nastaven NA hodnotu `true`. Wenn `pwzAssemblyIdentity2` bezieht sich auf eine höhere Versionsnummer `pfEquivalent` nastaven NA hodnotu `true` nur, wenn der Wert des `fUnified2` ist `true`.  
  
 Die `pResult` Parameter enthält spezielle Informationen, warum die zwei Assemblys als äquivalent betrachtet werden. Weitere Informationen finden Sie unter [AssemblyComparisonResult-Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [AssemblyComparisonResult-Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
