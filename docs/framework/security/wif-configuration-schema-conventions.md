---
title: "WIF-Konfigurationsschemakonventionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# WIF-Konfigurationsschemakonventionen
In diesem Thema werden die Konventionen erläutert, die während der verwendet werden Konfigurationsthemen Windows Identity Foundation \(WIF\) und beschreibt einige allgemeine Funktionen und Attribute, die in [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) und in den [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)\-Abschnitten verwendet werden.  
  
<a name="BKMK_Modes"></a>   
## Modi  
 Viele der WIF\-Konfigurationselemente haben ein `mode`\-Attribut.  Dieses Attribut steuert in der Regel, dem Klasse verwendet wird, um einen bestimmten Teil der Verarbeitung ausführen und das Konfigurationselemente als untergeordnete Elemente des aktuellen Elements zugelassen werden.  Ein Konfigurationsfehler wird ausgelöst, wenn Elemente, die in der Konfigurationsdatei enthalten sind, aufgrund der Moduseinstellungen ignoriert werden.  
  
<a name="BKMK_TimespanValues"></a>   
## TimeSpan\-Werte  
 Wo <xref:System.TimeSpan> verwendet wird, während der Typ eines Attributs, die <xref:System.TimeSpan.Parse%28System.String%29>\-Methode angezeigt, um die zulässige Format anzuzeigen.  Dieses Format passt sich an die folgenden Spezifikation an.  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 Beispielsweise "30 ", "30.00:00", "30.00:00: 00 " alle Durchschnitt 30 Tage; und "00:05", "00:05: 00 ", "0.00:05: 00.00 " Durchschnitt alle 5 Minuten.  
  
<a name="BKMK_CertificateReferences"></a>   
## Zertifikats\-Verweise  
 Einige Elementnehmenverweise zu den Zertifikaten mithilfe des `<certificateReference>`\-Elements.  Wenn sie ein Zertifikat verweisen, sind die folgenden Attribute verfügbar.  
  
|||  
|-|-|  
|`storeLocation`|Ein Wert der <xref:System.Security.Cryptography.X509Certificates.StoreLocation>\-Enumeration: `CurrentUser` oder `CurrentMachine`.|  
|`storeName`|Ein Wert der <xref:System.Security.Cryptography.X509Certificates.StoreName> enum; die hilfreich für diesen Kontext sind `My` und `TrustedPeople`.|  
|`x509FindType`|Ein Wert der <xref:System.Security.Cryptography.X509Certificates.X509FindType> enum; die hilfreich für diesen Kontext sind `FindBySubjectName` und `FindByThumbprint`.  Um die Wahrscheinlichkeit des Fehlers zu vermeiden, wird empfohlen `FindByThumbprint` der Typ in der Produktionsumgebung verwendet wird.|  
|`findValue`|Der Wert verwendet, um das Zertifikat, auf dem `x509FindType`\-Attribut zu suchen.  Um die Wahrscheinlichkeit des Fehlers zu vermeiden, wird empfohlen `FindByThumbprint` der Typ in der Produktionsumgebung verwendet wird.  Wenn `FindByThumbPrint` angegeben wurde, wird dieses Attribut einen Wert, der das Hexadezimalzeichenfolgenformular des Zertifikatsfingerabdrucks ist; beispielsweise "97249e1a5fa6bee5e515b82111ef524a4c91583f".|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## Benutzerdefinierte Typ\-Verweise  
 Einige Elementbezugsgewohnheitstypen mithilfe des `type`\-Attributs.  Dieses Attribut sollte den Namen des benutzerdefinierten Typs angeben.  Um einen Typ im globalen Assemblycache \(GAC\), sollte ein starker Name verwendet werden.  Um einen Typ aus einer Assembly im Behälterverzeichnis zu verweisen, wird ein einfacher durch die Assembly qualifizierten Verweis verwendet werden.  Die Typen, die im App\_Code\-\/verzeichnis definiert werden, werden auch verwiesen werden, indem Sie einfach den Typnamen ohne qualifizierenden Assembly angibt.  
  
 Benutzerdefinierte Typen müssen wurde vom angegebenen Typ abgeleitet werden und müssen einen Konstruktor `public` Standards bereitstellen \(0 Argument\).  
  
## Siehe auch  
 [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)   
 [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)