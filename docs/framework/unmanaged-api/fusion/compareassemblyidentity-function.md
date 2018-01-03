---
title: CompareAssemblyIdentity-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type: COM
f1_keywords: CompareAssemblyIdentity
helpviewer_keywords: CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 266868a65a0db75b57d46d92a469b4b6ceaa88e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="compareassemblyidentity-function"></a>CompareAssemblyIdentity-Funktion
Vergleicht zwei Assemblyidentitäten, um zu bestimmen, ob sie gleich sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwzAssemblyIdentity1`  
 [in] Die textbasierten Identität der ersten Assembly im Vergleich.  
  
 `fUnified1`  
 [in] Ein boolesches Flag, das Benutzer angegebene Vereinheitlichung für angibt `pwzAssemblyIdentity1`.  
  
 `pwzAssemblyIdentity2`  
 [in] Die textbasierten Identität der zweiten Assembly im Vergleich.  
  
 `fUnified2`  
 [in] Ein boolesches Flag, das Benutzer angegebene Vereinheitlichung für angibt `pwzAssemblyIdentity2`.  
  
 `pfEquivalent`  
 [out] Ein boolesches Flag, der angibt, ob die beiden Assemblys identisch sind.  
  
 `pResult`  
 [out] Ein [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) -Enumeration, die ausführliche Informationen zum Vergleich bereitstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 `pfEquivalent`Gibt einen booleschen Wert, der angibt, ob die beiden Assemblys identisch sind. `pResult`Gibt einen von der `AssemblyComparisonResult` -Werten, um eine detailliertere Begründung für den Wert des `pfEquivalent`.  
  
## <a name="remarks"></a>Hinweise  
 `CompareAssemblyIdentity`überprüft, ob `pwzAssemblyIdentity1` und `pwzAssemblyIdentity2` sind gleichwertig. `pfEquivalent`-Wert von `true` unter einer oder mehreren der folgenden Bedingungen:  
  
-   Die zwei Assemblyidentitäten entsprechen. Für Assemblys mit starkem Namen erfordert Äquivalenz Assemblyname, Version, öffentliches Schlüsseltoken und Kultur identisch sein. Für Assemblys mit einfachen Namen erfordert Äquivalenz eine Übereinstimmung bei der Assemblyname und Kultur entspricht.  
  
-   Beide Assemblyidentitäten verweisen auf Assemblys, die auf .NET Framework ausgeführt. Diese Bedingung gibt `true` , selbst wenn die Assemblyversionsnummern nicht übereinstimmen.  
  
-   Die beiden Assemblys sind nicht verwaltete Assemblys, aber `fUnified1` oder `fUnified2` wurde `true`.  
  
 Die `fUnified` Flag gibt an, dass alle Versionsnummern bis zu die Versionsnummer der Assembly mit starkem Namen als auf die Assembly mit starkem Namen gleichwertig betrachtet werden. Z. B. wenn der Wert der `pwzAssemblyIndentity1` ist "MyAssembly, Version = 3.0.0.0, Culture = Neutral, PublicKeyToken =...", und der Wert des `fUnified1` ist `true`, dies gibt an, dass alle Versionen von MyAssembly von Version 0.0.0.0 bis 3.0.0.0 werden soll als Äquivalent behandelt. In diesem Fall wenn `pwzAssemblyIndentity2` bezieht sich auf derselben Assembly wie `pwzAssemblyIndentity1`, außer dass es eine niedrigere Versionsnummer hat `pfEquivalent` auf festgelegt ist `true`. Wenn `pwzAssemblyIdentity2` bezieht sich auf eine höhere Versionsnummer `pfEquivalent` festgelegt ist, um `true` nur, wenn der Wert der `fUnified2` ist `true`.  
  
 Die `pResult` Parameter enthält bestimmte Informationen, warum die zwei Assemblys als äquivalent betrachtet werden. Weitere Informationen finden Sie unter [AssemblyComparisonResult-Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [AssemblyComparisonResult-Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
