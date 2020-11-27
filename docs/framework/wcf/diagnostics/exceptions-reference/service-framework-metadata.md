---
title: Dienstframeworkmetadaten
ms.date: 03/30/2017
ms.assetid: 76afc73a-0770-4084-93f3-6701a757911e
ms.openlocfilehash: 4133e758cde79294432ca501a10ed7ff20821954
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255766"
---
# <a name="service-framework-metadata"></a>Dienstframeworkmetadaten

Dieses Thema enthält alle von Dienstframeworkmetadaten erzeugten Ausnahmen.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|AsyncEndCalledOnWrongChannel|Async End hat einen Aufruf auf dem falschen Kanal platziert.|  
|AsyncEndCalledWithAnIAsyncResult|Async End hat einen Aufruf mit einem IAsyncResult-Wert aus einer anderen Begin-Methode platziert.|  
|AttemptedToGetContractTypeForButThatTypeIs1|Es wurde versucht, den Vertragstyp für das angegebene Element abzurufen. Der Typ ist jedoch kein ServiceContract und vererbt keinen ServiceContract.|  
|CannotHaveTwoOperationsWithTheSameName3|Es können keine zwei Vorgänge im selben Vertrag mit dem gleichen Namen bestehen. Die angegebenen Methoden im angegebenen Typ verstoßen gegen diese Regel. Ändern Sie den Namen eines der Vorgänge, indem Sie den Methodennamen ändern oder indem Sie die Name-Eigenschaft von OperationContractAttribute verwenden.|  
|CannotInheritTwoOperationsWithTheSameName3|Es können keine zwei Vorgänge mit dem gleichen Namen vererbt werden. Der angegebene Vorgang aus den angegebenen Verträgen verstößt gegen diese Regel. Ändern Sie den Namen eines der Vorgänge, indem Sie den Methodennamen ändern oder indem Sie die Name-Eigenschaft von OperationContractAttribute verwenden.|  
|CantCreateChannelWithManualAddressing|Es ist nicht möglich, einen Kanal für einen Vertrag zu erstellen, für den das Anforderung/Antwort-Prinzip und eine Bindung für die manuelle Adressierung erforderlich sind, der jedoch nur die Duplexkommunikation unterstützt.|  
|DuplicateBehavior1|Der Wert kann der Auflistung nicht hinzugefügt werden. Die Auflistung enthält bereits ein Element des angegebenen Typs. Die Auflistung unterstützt jedoch nur eine Instanz jedes Typs.|  
|InAContractInheritanceHierarchyIfParentHasCallbackChildMustToo|Da der angegebene Basisdienstvertrag einen angegebenen Rückrufvertrag aufweist, muss der angegebene abgeleitete Dienstvertrag ebenfalls entweder den angegebenen Typ oder einen abgeleiteten Typ als Rückrufvertrag angeben.|  
|InvalidAsyncBeginMethodSignatureForMethod2|Ungültige Signatur der async-Begin-Methode für die angegebene Methode in ServiceContract-Typ. Die Begin-Methode muss einen AsyncCallback und ein Objekt als die beiden letzten Argumente annehmen und ein IAsyncResult zurückgeben.|  
|InvalidAsyncEndMethodSignatureForMethod2|Ungültige Signatur der async-End-Methode für die angegebene Methode in ServiceContract-Typ. Die End-Methode muss ein IAsyncResult als letztes Argument annehmen.|  
|MessagePropertiesArraySize0|Das übergebene Array kann nicht alle Eigenschaften in dieser Auflistung aufnehmen.|  
|OneWayAndFaultsIncompatible2|Die angegebene Methode im angegebenen Typ ist als IsOneWay=true gekennzeichnet und deklariert mindestens ein FaultContractAttribute. Unidirektionale Methoden können FaultContractAttributes nicht deklarieren. Ändern Sie IsOneWay in False, oder entfernen Sie die FaultContractAttributes, um den Fehler zu beheben.|  
|UnsupportedWSDLOnlyOneMessage|Nicht unterstützte Web Services Description Language (WSDL). Bei Fehlernachrichten wird nur ein Nachrichtenteil unterstützt. Diese Fehlermeldung verweist auf mehr als einen Nachrichtenteil. Wenn Sie über Bearbeitungszugriff für die WSDL-Datei verfügen, können Sie das Problem beheben, indem Sie die zusätzlichen Nachrichtenteile entfernen, sodass die Fehlernachricht nur auf einen Teil verweist.|  
|UnsupportedWSDLTheFault|Nicht unterstützte Web Services Description Language (WSDL). Der Fehlernachrichtenteil muss auf ein Element verweisen. Diese Fehlermeldung verweist nicht auf ein Element. Wenn Sie über Bearbeitungszugriff für das WSDL-Dokument verfügen, können Sie das Problem beheben, indem Sie mit dem element-Attribut auf ein Schemaelement verweisen.|  
|WsdlImportErrorDependencyDetail|Fehler beim Importieren des angegebenen Elements, von dem der andere angegebene Wert abhängt. Der Xpath wird ebenfalls angegeben.|  
|XsdMissingRequiredAttribute1|Das angegebene erforderliche Attribut ist nicht vorhanden.|
