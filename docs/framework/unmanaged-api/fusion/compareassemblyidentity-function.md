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
ms.openlocfilehash: f6711902fb9d5c5c16084057b731746843cf0230
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108920"
---
# <a name="compareassemblyidentity-function"></a>CompareAssemblyIdentity-Funktion
Vergleicht zwei Assemblyidentitäten, um zu bestimmen, ob Sie äquivalent sind.  
  
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
 in Die Text Identität der ersten Assembly im Vergleich.  
  
 `fUnified1`  
 in Ein boolesches Flag, das eine vom Benutzer angegebene Vereinheitlichung für `pwzAssemblyIdentity1`angibt.  
  
 `pwzAssemblyIdentity2`  
 in Die Text Identität der zweiten Assembly im Vergleich.  
  
 `fUnified2`  
 in Ein boolesches Flag, das eine vom Benutzer angegebene Vereinheitlichung für `pwzAssemblyIdentity2`angibt.  
  
 `pfEquivalent`  
 vorgenommen Ein boolesches Flag, das angibt, ob die beiden Assemblys äquivalent sind.  
  
 `pResult`  
 vorgenommen Eine [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) -Enumeration, die ausführliche Informationen über den Vergleich enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 `pfEquivalent` gibt einen booleschen Wert zurück, der angibt, ob die beiden Assemblys äquivalent sind. `pResult` gibt einen der `AssemblyComparisonResult` Werte zurück, um einen detaillierteren Grund für den Wert von `pfEquivalent`zu erhalten.  
  
## <a name="remarks"></a>Hinweise  
 `CompareAssemblyIdentity` überprüft, ob `pwzAssemblyIdentity1` und `pwzAssemblyIdentity2` äquivalent sind. `pfEquivalent` wird unter einer oder mehreren der folgenden Bedingungen `true` festgelegt:  
  
- Die beiden Assemblyidentitäten sind gleichwertig. Für Assemblys mit starkem Namen müssen AssemblyName, Version, öffentliches Schlüssel Token und Kultur identisch sein. Bei einfachen benannten Assemblys erfordert die Äquivalenz eine Übereinstimmung mit dem Assemblynamen und der Kultur.  
  
- Beide Assemblyidentitäten verweisen auf Assemblys, die auf dem .NET Framework ausgeführt werden. Diese Bedingung gibt `true` zurück, auch wenn die Assemblyversionsnummern nicht stimmen.  
  
- Die beiden Assemblys sind keine verwalteten Assemblys, `fUnified1` oder `fUnified2` wurde jedoch auf `true`festgelegt.  
  
 Das Flag `fUnified` gibt an, dass alle Versionsnummern bis zur Versionsnummer der Assembly mit starkem Namen als Äquivalent zur Assembly mit starkem Namen betrachtet werden. Wenn der Wert von `pwzAssemblyIndentity1` z. b. "MyAssembly, Version = 3.0.0.0, Culture = neutral, PublicKeyToken =...." ist, und der Wert von `fUnified1` `true`ist, bedeutet dies, dass alle Versionen von myAssembly von Version 0.0.0.0 zu 3.0.0.0 wie folgt behandelt werden: entsprechen. Wenn `pwzAssemblyIndentity2` in einem solchen Fall auf dieselbe Assembly verweist wie `pwzAssemblyIndentity1`, mit der Ausnahme, dass Sie eine niedrigere Versionsnummer aufweist, wird `pfEquivalent` auf `true`festgelegt. Wenn `pwzAssemblyIdentity2` auf eine höhere Versionsnummer verweist, wird `pfEquivalent` nur auf `true` festgelegt, wenn der Wert `fUnified2` `true`ist.  
  
 Der `pResult`-Parameter enthält spezifische Informationen darüber, warum die beiden Assemblys als gleichwertig oder nicht äquivalent angesehen werden. Weitere Informationen finden Sie unter [AssemblyComparisonResult-Enumeration](assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
- [AssemblyComparisonResult-Enumeration](assemblycomparisonresult-enumeration.md)
