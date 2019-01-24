---
title: WIF-Konfigurationsschemakonventionen
ms.date: 03/30/2017
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
author: BrucePerlerMS
ms.openlocfilehash: acdce1f0ae35713dd4955e1353e0a83000898408
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711394"
---
# <a name="wif-configuration-schema-conventions"></a>WIF-Konfigurationsschemakonventionen
In diesem Thema werden Konventionen erläutert, die in den Themen zur Konfiguration von Windows Identity Foundation (WIF) verwendet werden, sowie einige allgemeine Funktionen und Attribute beschrieben, die in den Abschnitten [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) und [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) verwendet werden.  
  
<a name="BKMK_Modes"></a>   
## <a name="modes"></a>Modi  
 Viele der Elemente der WIF-Konfiguration verfügen über ein `mode`-Attribut. Dieses Attribut steuert in der Regel, welche Klasse verwendet wird, um einen bestimmten Teil der Verarbeitung durchzuführen, und welche Konfigurationselemente als untergeordnete Elemente des aktuellen Elements zulässig sind. Es wird ein Konfigurationsfehler ausgelöst, wenn Elemente, die in der Konfigurationsdatei enthalten sind, aufgrund der Moduseinstellungen ignoriert werden.  
  
<a name="BKMK_TimespanValues"></a>   
## <a name="timespan-values"></a>TimeSpan-Werte  
 Wo <xref:System.TimeSpan> als Typ eines Attributs verwendet wird, finden Sie das zulässige Format in der <xref:System.TimeSpan.Parse%28System.String%29>-Methode. Dieses Format entspricht der folgenden Spezifikation.  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 Beispielsweise bedeuten „30“, „30.00:00“, „30.00:00:00“ alle 30 Tage; und „00:05“, „00: 05:00“, „0.00:05:00.00“ bedeuten alle 5 Minuten.  
  
<a name="BKMK_CertificateReferences"></a>   
## <a name="certificate-references"></a>Zertifikatverweise  
 Mehrere Elemente verweisen auf Zertifikate, die das `<certificateReference>`-Element verwenden. Wenn Sie auf ein Zertifikat verweisen, sind die folgenden Attribute verfügbar.  
  
|||  
|-|-|  
|`storeLocation`|Ein Wert der <xref:System.Security.Cryptography.X509Certificates.StoreLocation>-Enumeration: `CurrentUser` oder `CurrentMachine`.|  
|`storeName`|Ein Wert der <xref:System.Security.Cryptography.X509Certificates.StoreName>-Enumeration; besonders hilfreich für diesen Kontext sind `My` und `TrustedPeople`.|  
|`x509FindType`|Ein Wert der <xref:System.Security.Cryptography.X509Certificates.X509FindType>-Enumeration; besonders hilfreich für diesen Kontext sind `FindBySubjectName` und `FindByThumbprint`. Um die Fehlerwahrscheinlichkeit zu vermeiden, wird empfohlen, den `FindByThumbprint`-Typ in Produktionsumgebungen zu verwenden.|  
|`findValue`|Der Wert, mit dem das Zertifikat auf Basis des `x509FindType`-Attributs gefunden werden soll. Um die Fehlerwahrscheinlichkeit zu vermeiden, wird empfohlen, den `FindByThumbprint`-Typ in Produktionsumgebungen zu verwenden. Wenn `FindByThumbPrint` angegeben wird, nimmt dieses Attribut einen Wert an, der das hexadezimale Zeichenfolgenformat des Zertifikatfingerabdrucks darstellt, z.B. „97249e1a5fa6bee5e515b82111ef524a4c91583f“.|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## <a name="custom-type-references"></a>Benutzerdefinierte Typverweise  
 Mehrere Elemente verweisen mithilfe des `type`-Attributs auf benutzerdefinierte Typen. Dieses Attribut sollte den Namen des benutzerdefinierten Typs angeben. Um auf einen Typ aus dem globalen Assemblycache (GAC) zu verweisen, sollte ein starker Name verwendet werden. Um auf einen Typ aus einer Assembly im „Bin/“-Verzeichnis zu verweisen, kann ein einfacher Verweis mit Assemblyqualifikation verwendet werden. Um auf Typen zu verweisen, die in einem „App_Code/“-Verzeichnis definiert sind, kann auch einfach der Typname ohne Assemblyqualifikation verwendet werden.  
  
 Benutzerdefinierte Typen müssen aus dem angegebenen Typ abgeleitet werden und einen `public`-Standardkonstruktor (0-Argument) bereitstellen.  
  
## <a name="see-also"></a>Siehe auch
- [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)
- [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)
