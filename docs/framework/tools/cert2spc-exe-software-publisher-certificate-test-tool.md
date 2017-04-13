---
title: "Cert2spc.exe (Software Publisher Certificate Test Tool) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "SPC"
  - "Software Publisher Certificate Test tool"
  - "Software Publisher Certificate"
  - "Cert2spc.exe"
  - "certificates, Software Publisher's Certificate"
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# Cert2spc.exe (Software Publisher Certificate Test Tool)
Das Software Publisher Certificate Test\-Tool erstellt ein SPC \(Software Publisher's Certificate, Softwareherausgeberzertifikat\) aus einem oder mehreren X.509\-Zertifikaten.  "Cert2spc.exe" wird ausschließlich zu Textzwecken verwendet.  Sie erhalten ein gültiges SPC von einer Zertifizierungsstelle, beispielsweise VeriSign oder Thawte.  Weitere Informationen zum Erstellen von X.509\-Zertifikaten finden Sie unter [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md).  
  
 Dieses Tool wird automatisch mit Visual Studio installiert.  Zum Ausführen des Tools verwenden Sie die Developer\-Eingabeaufforderung \(oder die Visual Studio\-Eingabeaufforderung in Windows 7\).  Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## Syntax  
  
```  
  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### Parameter  
  
|Argument|Beschreibung|  
|--------------|------------------|  
|`certN.cer`|Der Name eines X.509\-Zertifikats, das in die SPC\-Datei eingebunden werden soll.  Sie können mehrere Namen angeben, die durch Leerzeichen voneinander getrennt werden müssen.|  
|`crlN.crl`|Der Name einer Zertifikatssperrliste, die in die SPC\-Datei aufgenommen werden soll.  Sie können mehrere Namen angeben, die durch Leerzeichen voneinander getrennt werden müssen.|  
|`outputSPCfile.spc`|Der Name des PKCS \#7\-Objekts, das die X.509\-Zertifikate enthält.|  
  
|Option|Beschreibung|  
|------------|------------------|  
|**\/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
## Beispiele  
 Der folgende Befehl erstellt ein SPC aus `myCertificate.cer` und platziert es in `mySPCFile.spc`.  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 Der folgende Befehl erstellt ein SPC aus `oneCertificate.cer` und `twoCertificate.cer` und platziert es in `mySPCFile.spc`.  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## Siehe auch  
 [Tools](../../../docs/framework/tools/index.md)   
 [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)   
 [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md)