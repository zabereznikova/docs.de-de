---
title: 'Gewusst wie: Erkennen von Netzwerkverfügbarkeit und Adressänderungen'
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: d4377115-4a76-4848-ab23-4898d65c771c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: c0357c4000a7efdb838a40f2f3f907c1dd313c58
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193121"
---
# <a name="how-to-detect-network-availability-and-address-changes"></a><span data-ttu-id="0c66b-102">Gewusst wie: Erkennen von Netzwerkverfügbarkeit und Adressänderungen</span><span class="sxs-lookup"><span data-stu-id="0c66b-102">How to: Detect Network Availability and Address Changes</span></span>
<span data-ttu-id="0c66b-103">In diesem Beispiel wird gezeigt, wie Änderungen in der Netzwerkadresse einer Schnittstelle erkannt werden können.</span><span class="sxs-lookup"><span data-stu-id="0c66b-103">This sample shows how to detect changes in the network address of an interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c66b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c66b-104">Example</span></span>  
  
```  
using System;  
using System.Net;  
using System.Net.NetworkInformation;  
  
namespace Examples.Net.AddressChanges  
{  
    public class NetworkingExample  
    {  
        public static void Main()  
        {  
            NetworkChange.NetworkAddressChanged += new   
             NetworkAddressChangedEventHandler(AddressChangedCallback);  
            Console.WriteLine("Listening for address changes. Press any key to exit.");  
            Console.ReadLine();  
        }  
        static void AddressChangedCallback(object sender, EventArgs e)  
        {  
  
            NetworkInterface[] adapters = NetworkInterface.GetAllNetworkInterfaces();  
            foreach(NetworkInterface n in adapters)  
            {  
                Console.WriteLine("   {0} is {1}", n.Name, n.OperationalStatus);  
            }  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0c66b-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0c66b-105">Compiling the Code</span></span>  
 <span data-ttu-id="0c66b-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0c66b-106">This example requires:</span></span>  
  
-   <span data-ttu-id="0c66b-107">Verweise auf den Namespace **System.Net**</span><span class="sxs-lookup"><span data-stu-id="0c66b-107">References to the **System.Net** namespace.</span></span>
