---
title: "Vorgehensweise: Zug&#228;nglichmachen von X.509-Zertifikaten f&#252;r WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zertifikate [WCF], Ermöglichen des Zugriffs auf X.509-Zertifikate für WCF"
  - "X.509-Zertifikate [WCF]"
  - "X.509-Zertifikate [WCF], Ermöglichen des Zugriffs für WCF"
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Vorgehensweise: Zug&#228;nglichmachen von X.509-Zertifikaten f&#252;r WCF
Damit ein X.509\-Zertifikat für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zugänglich ist, muss der Name und der Speicherort des Zertifikats im Anwendungscode angegeben werden.In bestimmten Fällen benötigt die Prozessidentität Zugriff auf die Datei, die den zugeordneten privaten Schlüssel für das X.509\-Zertifikat enthält.Um den privaten Schlüssel zu erhalten, der einem X.509\-Zertifikat in einem Zertifikatspeicher zugeordnet ist, benötigt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die entsprechenden Berechtigungen.Standardmäßig können nur der Besitzer und das Systemkonto auf den privaten Schlüssel eines Zertifikats zugreifen.  
  
### So machen Sie X.509\-Zertifikate für WCF zugänglich  
  
1.  Erteilen Sie dem Konto, unter dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ausgeführt wird, Schreibzugriff auf die Datei, die den zugeordneten privaten Schlüssel für das X.509\-Zertifikat enthält.  
  
    1.  Ermitteln Sie, ob [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Lesezugriff auf den privaten Schlüssel für das X.509\-Zertifikat benötigt.  
  
         Die folgende Tabelle beschreibt, ob ein privater Schlüssel bei der Verwendung eines X.509\-Zertifikats verfügbar sein muss.  
  
        |Verwendung des X.509\-Zertifikats|Privater Schlüssel|  
        |---------------------------------------|------------------------|  
        |Digitales Signieren einer ausgehenden SOAP\-Nachricht.|Ja|  
        |Überprüfen der Signatur einer eingehenden SOAP\-Nachricht.|Nein|  
        |Verschlüsseln einer ausgehenden SOAP\-Nachricht.|Nein|  
        |Verschlüsseln einer eingehenden SOAP\-Nachricht.|Ja|  
  
    2.  Ermitteln Sie den Ort und Namen des Zertifikatspeicherspeichers, in dem sich das Zertifikat befindet.  
  
         Der Zertifikatspeicher, in dem das Zertifikat gespeichert ist, wird entweder im Anwendungscode oder in einer Konfiguration angegeben.Im folgenden Beispiel wird angegeben, dass sich das Zertifikat im `CurrentUser`\-Zertifikatsspeicher mit dem Namen `My` befindet.  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3.  Ermitteln Sie, wo sich der private Schlüssel für das Zertifikat auf dem Computer befindet. Verwenden Sie dazu das Tool [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md).  
  
         Für das Tool [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) wird der Name und der Ort des Zertifikatsspeichers und eine Angabe benötigt, die das Zertifikat eindeutig identifiziert.Als eindeutiger Bezeichner werden der Antragstellername oder der Fingerabdruck des Zertifikats von dem Tool akzeptiert.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Vorgehensweise zum Ermitteln des Fingerabdrucks für ein Zertifikat finden Sie unter [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
         Im folgenden Codebeispiel wird mithilfe des Tools [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) der Speicherort des privaten Schlüssels für ein Zertifikat im Speicher `My` in `CurrentUser` mit einem Fingerabdruck `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d` ermittelt.  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  Ermitteln Sie das Konto, unter dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ausgeführt wird.  
  
         In der folgenden Tabelle werden die Konten beschrieben, unter denen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in einem bestimmten Szenario ausgeführt wird.  
  
        |Szenario|Prozessidentität|  
        |--------------|----------------------|  
        |Client \(Konsole oder WinForms\-Anwendung\)|Aktuell angemeldeter Benutzer|  
        |Selbst gehosteter Dienst|Aktuell angemeldeter Benutzer|  
        |Dienst, der in IIS 6.0 \([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]\) oder IIS 7.0 \([!INCLUDE[wv](../../../../includes/wv-md.md)]\) gehostet wird.|NETZWERKDIENST|  
        |Dienst, der in IIS 5.X \([!INCLUDE[wxp](../../../../includes/wxp-md.md)]\) gehostet wird.|Wird durch das `<processModel>`\-Element in der Datei Machine.config gesteuert.ASPNET ist das Standardkonto.|  
  
    5.  Erteilen Sie der Datei, die den privaten Schlüssel für das Konto enthält, unter dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ausgeführt wird, mithilfe eines Tools wie cacls.exe Lesezugriff.  
  
         Im folgenden Codebeispiel wird die Zugriffssteuerungsliste \(\/E\) für die angegebene Datei bearbeitet, um \(\/G\), dem NETZWERKDIENST\-Konto, Lesezugriff \(:R\) auf die Datei zu erteilen.  
  
        ```  
        cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
        ```  
  
## Siehe auch  
 [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)   
 [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)   
 [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)