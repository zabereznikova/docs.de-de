---
title: "FindPrivateKey | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "FindPrivateKey"
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# FindPrivateKey
Es kann schwierig sein, den Speicherort und Namen der Privatschlüsseldatei zu finden, die einem bestimmten X.509\-Zertifikat im Zertifikatspeicher zugeordnet ist.Das Tool FindPrivateKey.exe erleichtert diesen Prozess.  
  
> [!IMPORTANT]
>  FindPrivateKey ist ein Beispiel, das vor der Verwendung kompiliert werden muss.Der Abschnitt "Erstellen des FindPrivateKey\-Projekts" enthält weitere Informationen darüber, wie man das FindPrivateKey\-Tool erstellt.  
  
 X.509\-Zertifikate werden von einem Administrator oder einem beliebigen Benutzer auf dem Computer installiert.Auf das Zertifikat kann jedoch von einem Dienst zugegriffen werden, der unter einem anderen Konto ausgeführt wird \(beispielsweise ASPNET unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] oder die NETWORK SERVICE\-Konten unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]\).  
  
 Dieses Konto verfügt möglicherweise nicht über Zugriff auf die Privatschlüsseldatei, da das Zertifikat nicht ursprünglich von diesem Konto installiert wurde.Das Tool FindPrivateKey gibt den Speicherort der Privatschlüsseldatei eines X.509\-Zertifikats an.Sie können Berechtigungen in dieser Datei hinzufügen oder entfernen, wenn Sie den Speicherort der Privatschlüsseldatei der jeweiligen X.509\-Zertifikate kennen.  
  
 In den Beispielen, in denen Zertifikate für die Sicherheit verwendet werden, wird das Tool FindPrivateKey in der Datei "Setup.bat" verwendet.Wenn die Privatschlüsseldatei gefunden wurde, können Sie mit anderen Tools wie Cacls.exe die entsprechenden Zugriffsrechte für die Datei festlegen.  
  
 Stellen Sie beim Ausführen eines [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Diensts unter einem Benutzerkonto sicher, beispielsweise einer selbst gehosteten ausführbaren Datei, dass das Benutzerkonto nur über Lesezugriff auf die Datei verfügt.Beim Ausführen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts unter Internetinformationsdienste \(IIS\) lauten die Standardkonten, unter denen der Dienst ausgeführt wird, ASPNET unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] bzw. NETWORK SERVICE unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. Diese verfügen standardmäßig nicht über Zugriff auf die Privatschlüsseldatei.  
  
## Beispiele  
 Beim Zugreifen auf ein Zertifikat, für das der Prozess über keine Leseberechtigung verfügt, wird eine Ausnahmemeldung angezeigt, ähnlich wie im folgenden Beispiel.  
  
```  
System.ArgumentException was unhandled  
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."  
Source="System.ServiceModel"  
```  
  
 Wenn dies auftritt, suchen Sie mithilfe des Tools FindPrivateKey die Privatschlüsseldatei, und legen Sie dann die Zugriffsberechtigung für den Prozess fest, unter dem der Dienst ausgeführt wird.Dies kann beispielsweise mit dem Tool Cacls.exe erfolgen, wie im folgenden Beispiel dargestellt.  
  
```  
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
```  
  
#### So erstellen Sie das FindPrivateKey\-Projekt  
  
1.  Öffnen Sie [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], und navigieren Sie zum sprachspezifischen Unterverzeichnis im Verzeichnis, in dem Sie das Beispiel installiert haben.  
  
2.  Doppelklicken Sie auf das Symbol für die SLN\-Datei, um diese in Visual Studio zu öffnen.  
  
3.  Wählen Sie im Menü **Erstellen** die Option **Projektmappe neu erstellen** aus.Die Clientprogrammdateien werden in client\\bin erstellt, und die Hilfsprogrammdateien werden in service\\bin erstellt.  
  
4.  Beim Erstellen der Projektmappe wird die Datei "FindPrivateKey.exe" erstellt.  
  
## Konventionen: Befehlszeileneinträge  
 "\[*option*\]" stellt einen optionalen Satz von Parametern dar.  
  
 "{*option*}" stellt einen obligatorischen Satz von Parametern dar.  
  
 "*option1* &#124; *option2*" stellt eine Auswahl zwischen zwei Optionssätzen dar.  
  
 "\<*value*\>" stellt einen einzugebenden Parameterwert dar.  
  
## Verwendung  
  
```  
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
 Dabei gilt:  
  
```  
       <subjectName> The subject name of the certificate  
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)  
       -f            output file name only  
       -d            output directory only  
       -a            output absolute file name  
```  
  
 Wenn keine Parameter bei der Eingabeaufforderung angegeben werden, wird dieser Hilfetext angezeigt.  
  
## Beispiele  
 In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragstellernamen "CN\=localhost" im persönlichen Speicher des aktuellen Benutzers gesucht.FindPrivateKey My CurrentUser \-n "CN\=localhost".  
  
 In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragstellernamen "CN\=localhost" im persönlichen Speicher des aktuellen Benutzers gesucht und der vollständige Verzeichnispfad ausgegeben.  
  
```  
User.FindPrivateKey My CurrentUser -n "CN=localhost" -a  
  
```  
  
 In diesem Beispiel wird der Dateiname des Zertifikats mit dem Fingerabdruck "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" im persönlichen Speicher des lokalen Computers gesucht.  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –c  
```  
  
## Siehe auch