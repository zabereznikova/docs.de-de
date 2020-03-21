---
title: 'Vorgehensweise: Zugänglichmachen von X.509-Zertifikaten für WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: 14f2242ab55795c74fa169382fef846bc0e60ace
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184894"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a>Vorgehensweise: Zugänglichmachen von X.509-Zertifikaten für WCF
Damit ein X.509-Zertifikat für Windows Communication Foundation (WCF) zugänglich ist, muss Anwendungscode den Namen und den Speicherort des Zertifikatspeichers angeben. In bestimmten Fällen benötigt die Prozessidentität Zugriff auf die Datei, die den zugeordneten privaten Schlüssel für das X.509-Zertifikat enthält. Um den privaten Schlüssel zu erhalten, der einem X.509-Zertifikat in einem Zertifikatspeicher zugeordnet ist, muss WCF über die entsprechende Berechtigung verfügen. Standardmäßig können nur der Besitzer und das Systemkonto auf den privaten Schlüssel eines Zertifikats zugreifen.  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a>So machen Sie X.509-Zertifikate für WCF zugänglich  
  
1. Geben Sie dem Konto, unter dem WCF ausgeführt wird, Lesezugriff auf die Datei, die den privaten Schlüssel enthält, der dem X.509-Zertifikat zugeordnet ist.  
  
    1. Bestimmen Sie, ob WCF Lesezugriff auf den privaten Schlüssel für das X.509-Zertifikat benötigt.  
  
         Die folgende Tabelle beschreibt, ob ein privater Schlüssel bei der Verwendung eines X.509-Zertifikats verfügbar sein muss.  
  
        |Verwendung des X.509-Zertifikats|Privater Schlüssel|  
        |---------------------------|-----------------|  
        |Digitales Signieren einer ausgehenden SOAP-Nachricht.|Ja|  
        |Überprüfen der Signatur einer eingehenden SOAP-Nachricht.|Nein |  
        |Verschlüsseln einer ausgehenden SOAP-Nachricht.|Nein |  
        |Verschlüsseln einer eingehenden SOAP-Nachricht.|Ja|  
  
    2. Ermitteln Sie den Ort und Namen des Zertifikatspeicherspeichers, in dem sich das Zertifikat befindet.  
  
         Der Zertifikatspeicher, in dem das Zertifikat gespeichert ist, wird entweder im Anwendungscode oder in einer Konfiguration angegeben. Im folgenden Beispiel wird angegeben, dass sich das Zertifikat im `CurrentUser`-Zertifikatsspeicher mit dem Namen `My` befindet.  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3. Bestimmen Sie mithilfe des [Werkzeugs FindPrivateKey,](../../../../docs/framework/wcf/samples/findprivatekey.md) wo sich der private Schlüssel für das Zertifikat auf dem Computer befindet.  
  
         Das [FindPrivateKey-Tool](../../../../docs/framework/wcf/samples/findprivatekey.md) erfordert den Namen des Zertifikatspeichers, den Speicherort des Zertifikatspeichers und etwas, das das Zertifikat eindeutig identifiziert. Als eindeutiger Bezeichner werden der Antragstellername oder der Fingerabdruck des Zertifikats von dem Tool akzeptiert. Weitere Informationen zum Bestimmen des Fingerabdrucks für ein Zertifikat finden Sie unter [Gewusst wie: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
         Im folgenden Codebeispiel wird das [Werkzeug FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) verwendet, um den `My` Speicherort `CurrentUser` des privaten `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`Schlüssels für ein Zertifikat im Speicher in mit einem Fingerabdruck von zu bestimmen.  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. Bestimmen Sie das Konto, unter dem WCF ausgeführt wird.  
  
         In der folgenden Tabelle ist das Konto aufgeführt, unter dem WCF für ein bestimmtes Szenario ausgeführt wird.  
  
        |Szenario|Prozessidentität|  
        |--------------|----------------------|  
        |Client (Konsole oder WinForms-Anwendung)|Aktuell angemeldeter Benutzer|  
        |Selbst gehosteter Dienst|Aktuell angemeldeter Benutzer|  
        |Dienst, der in IIS 6.0 (Windows Server 2003) oder IIS 7.0 (Windows Vista) gehostet wird.|NETZWERKDIENST|  
        |Dienst, der in IIS 5.X (Windows XP) gehostet wird.|Wird durch das `<processModel>`-Element in der Datei Machine.config gesteuert. ASPNET ist das Standardkonto.|  
  
    5. Gewähren Sie Lesezugriff auf die Datei, die den privaten Schlüssel enthält, auf das Konto, unter dem WCF ausgeführt wird, mit einem Tool wie icacls.exe.  
  
         Im folgenden Codebeispiel wird die DACL (Discretionary Access Control List) für die angegebene Datei für den Lesezugriff (:R) des NETWORK SERVICE-Kontos auf die Datei erweitert.  
  
        ```console
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a>Weitere Informationen

- [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)
- [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
