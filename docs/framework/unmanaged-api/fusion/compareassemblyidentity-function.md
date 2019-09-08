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
ms.openlocfilehash: b52d3af38bd09ce5864c25d27e148dbd7f4639b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795447"
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
 in Ein boolesches Flag, das die vom Benutzer angegebene Vereinheitlichung `pwzAssemblyIdentity1`für angibt.  
  
 `pwzAssemblyIdentity2`  
 in Die Text Identität der zweiten Assembly im Vergleich.  
  
 `fUnified2`  
 in Ein boolesches Flag, das die vom Benutzer angegebene Vereinheitlichung `pwzAssemblyIdentity2`für angibt.  
  
 `pfEquivalent`  
 vorgenommen Ein boolesches Flag, das angibt, ob die beiden Assemblys äquivalent sind.  
  
 `pResult`  
 vorgenommen Eine [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) -Enumeration, die ausführliche Informationen über den Vergleich enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 `pfEquivalent`Gibt einen booleschen Wert zurück, der angibt, ob die beiden Assemblys äquivalent sind. `pResult`Gibt einen der `AssemblyComparisonResult` -Werte zurück, um einen detaillierteren Grund für den Wert von `pfEquivalent`zu erhalten.  
  
## <a name="remarks"></a>Hinweise  
 `CompareAssemblyIdentity`überprüft, `pwzAssemblyIdentity1` ob `pwzAssemblyIdentity2` und äquivalent sind. `pfEquivalent`wird unter einer `true` oder mehreren der folgenden Bedingungen auf festgelegt:  
  
- Die beiden Assemblyidentitäten sind gleichwertig. Für Assemblys mit starkem Namen müssen AssemblyName, Version, öffentliches Schlüssel Token und Kultur identisch sein. Bei einfachen benannten Assemblys erfordert die Äquivalenz eine Übereinstimmung mit dem Assemblynamen und der Kultur.  
  
- Beide Assemblyidentitäten verweisen auf Assemblys, die auf dem .NET Framework ausgeführt werden. Diese Bedingung gibt `true` auch dann zurück, wenn die Assemblyversionsnummern nicht stimmen.  
  
- Die beiden Assemblys sind keine verwalteten Assemblys, `fUnified1` aber `true`oder `fUnified2` wurde auf festgelegt.  
  
 Das `fUnified` -Flag gibt an, dass alle Versionsnummern bis zur Versionsnummer der Assembly mit starkem Namen als Äquivalent zur Assembly mit starkem Namen betrachtet werden. Wenn der Wert von `pwzAssemblyIndentity1` z. b. "MyAssembly, Version = 3.0.0.0, Culture = neutral, PublicKeyToken =...." lautet und der Wert von `fUnified1` ist `true`, bedeutet dies, dass alle Versionen von myAssembly von Version 0.0.0.0 zu 3.0.0.0 wird als gleichwertig behandelt. In einem solchen Fall, wenn `pwzAssemblyIndentity2` auf dieselbe Assembly verweist wie `pwzAssemblyIndentity1`, mit der Ausnahme, dass Sie eine niedrigere Versionsnummer `pfEquivalent` aufweist, wird `true`auf festgelegt. Wenn `pwzAssemblyIdentity2` auf eine höhere Versionsnummer verweist, `pfEquivalent` wird nur auf `true` festgelegt, wenn der `fUnified2` Wert `true`von auf festgelegt ist.  
  
 Der `pResult` -Parameter enthält spezifische Informationen darüber, warum die beiden Assemblys als gleichwertig oder nicht äquivalent angesehen werden. Weitere Informationen finden Sie unter [AssemblyComparisonResult-Enumeration](assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
- [AssemblyComparisonResult-Enumeration](assemblycomparisonresult-enumeration.md)
