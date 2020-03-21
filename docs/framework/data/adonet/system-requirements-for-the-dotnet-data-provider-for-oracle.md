---
title: Systemanforderungen für den.NET Framework-Datenanbieter für Oracle
ms.date: 03/30/2017
ms.assetid: 054f76b9-1737-43f0-8160-84a00a387217
ms.openlocfilehash: dab3378d3022c01c674640201a67f3bdbb4f571f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174250"
---
# <a name="system-requirements-for-the-net-framework-data-provider-for-oracle"></a>Systemanforderungen für den.NET Framework-Datenanbieter für Oracle

Der .NET Framework-Datenanbieter für Oracle erfordert Microsoft Data Access Components (MDAC), Version 2.6 oder höher. MDAC 2.8 mit SP1 wird empfohlen.  
  
 Ebenso muss der Oracle 8i-Client, Release 3 (8.1.7) oder höher, installiert sein.  
  
 Oracle Clientsoftware, die älter als Version Oracle 9i ist, kann nicht auf UTF16-Datenbanken zugreifen, weil UTF16 eine neue Funktion in Oracle 9i ist. Wenn Sie diese Funktion verwenden möchten, müssen Sie die Clientsoftware auf Oracle 9i oder höher aktualisieren.  
  
## <a name="working-with-the-data-provider-for-oracle-and-unicode-data"></a>Arbeiten mit dem Datenanbieter für Oracle- und Unicode-Daten  

Im Folgenden finden Sie eine Liste von Unicode-bezogenen Problemen, die Sie bei der Arbeit mit dem .NET Framework-Datenanbieter für Oracle- und Oracle-Clientbibliotheken berücksichtigen sollten. Weitere Informationen finden Sie in der Oracle-Dokumentation.  
  
### <a name="setting-the-unicode-value-in-a-connection-string-attribute"></a>Festlegen des Unicode-Werts in einem Verbindungszeichenfolgen-Attribut  

Beim Arbeiten mit Oracle können Sie das Verbindungszeichenfolgen-Attribut   
  
`Unicode=True`
  
verwenden, um die Oracle-Clientbibliotheken im UTF-16-Modus zu initialisieren. Dadurch müssen die Oracle-Clientbibliotheken UTF-16-Zeichenfolgen (die UCS-2 sehr ähnlich sind) anstelle von Multi-Byte-Zeichenfolgen akzeptieren. Der Datenanbieter für Oracle kann somit immer eine beliebigen Oracle-Codepage ohne zusätzliche Umwandlungen verwenden. Diese Konfiguration funktioniert nur, wenn Oracle 9i-Clients für die Kommunikation mit einer Oracle 9i-Datenbank mit dem alternativen Zeichensatz AL16UTF16 verwendet werden. Wenn ein Oracle 9i-Client mit einem Oracle 9i-Server kommuniziert, sind zusätzliche Ressourcen erforderlich, um die Unicode **CommandText-Werte** in den entsprechenden Multibyte-Zeichensatz zu konvertieren, den der Oracle9i-Server verwendet. Durch Hinzufügen von `Unicode=True` zur Verbindungszeichenfolge kann dies vermieden werden, wenn Sie über eine sichere Konfiguration verfügen.  
  
### <a name="mixing-versions-of-oracle-client-and-oracle-server"></a>Verwenden verschiedener Versionen von Oracle Client und Oracle Server  

Oracle 8i-Clients können nicht auf **NCHAR-,** **NVARCHAR2-** oder **NCLOB-Daten** in Oracle 9i-Datenbanken zugreifen, wenn der nationale Zeichensatz des Servers als AL16UTF16 (Standardeinstellung für Oracle 9i) angegeben ist. Da die Unterstützung für den UTF-16-Zeichensatz erst ab Oracle 9i eingeführt wurde, können Oracle 8i-Clients ihn nicht lesen.  
  
### <a name="working-with-utf-8-data"></a>Arbeiten mit UTF-8-Daten  

Wenn Sie den alternativen Zeichensatz festlegen möchten, legen Sie den Registrierungsschlüssel HKEY_LOCAL_MACHINE\SOFTWARE\ORACLE\HOMEID\NLS_LANG auf UTF8 fest. Weitere Informationen finden Sie in den Oracle-Installationshinweisen für Ihre Plattform. Die Standardeinstellung ist der primäre Zeichensatz der Sprache, in der Sie die Oracle Clientsoftware installieren. Wenn Sie die Sprache nicht entsprechend dem Zeichensatz der Landessprache für die Datenbank festlegen, mit der Sie die Verbindung herstellen, führt dies dazu, dass die Parameter- und Spaltenbindungen Daten im primären Zeichensatz der Datenbank und nicht im nationalen Zeichensatz senden oder empfangen.  
  
### <a name="oraclelob-can-only-update-full-characters"></a>OracleLob kann nur vollständige Zeichen aktualisieren.  

Aus Gründen der <xref:System.Data.OracleClient.OracleLob> Benutzerfreundlichkeit erbt das Objekt von der .NET Framework Stream-Klasse und stellt **ReadByte-** und **WriteByte-Methoden** bereit. Außerdem werden Methoden wie **CopyTo** und **Erase**implementiert, die an Abschnitten von Oracle **LOB-Objekten** arbeiten. Im Gegensatz dazu bietet Oracle Client-Software eine Reihe von APIs für die Arbeit mit **Zeichen-LOB**s (**CLOB** und **NCLOB**). Allerdings unterstützen diese APIs nur vollständige Zeichen. Aufgrund dieses Unterschieds implementiert der Datenanbieter für Oracle Unterstützung für **Read** und **ReadByte,** um byteweise mit UTF-16-Daten zu arbeiten. Die anderen Methoden des **OracleLob-Objekts** lassen jedoch nur vollstellige Vorgänge zu.  
  
## <a name="see-also"></a>Weitere Informationen

- [Oracle und ADO.NET](oracle-and-adonet.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
