---
title: OLE DB-Schemaauflistungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 33e794559abd7f619f7431683f06e59705b57d41
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="0b6a7-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="0b6a7-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="0b6a7-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="0b6a7-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="0b6a7-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="0b6a7-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="0b6a7-105">Der Microsoft SQL Server OLE DB-Treiber unterstützt die folgenden spezifischen schemaauflistungen zusätzlich zu den allgemeinen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="0b6a7-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="0b6a7-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0b6a7-106">Tables</span></span>  
  
-   <span data-ttu-id="0b6a7-107">Columns</span><span class="sxs-lookup"><span data-stu-id="0b6a7-107">Columns</span></span>  
  
-   <span data-ttu-id="0b6a7-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b6a7-108">Procedures</span></span>  
  
-   <span data-ttu-id="0b6a7-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0b6a7-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="0b6a7-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="0b6a7-110">Catalog</span></span>  
  
-   <span data-ttu-id="0b6a7-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="0b6a7-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="0b6a7-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0b6a7-112">Tables</span></span>  
  
|<span data-ttu-id="0b6a7-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-113">ColumnName</span></span>|<span data-ttu-id="0b6a7-114">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-115">TABLE_CATALOG</span></span>|<span data-ttu-id="0b6a7-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-116">String</span></span>|  
|<span data-ttu-id="0b6a7-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-118">String</span></span>|  
|<span data-ttu-id="0b6a7-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-119">TABLE_NAME</span></span>|<span data-ttu-id="0b6a7-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-120">String</span></span>|  
|<span data-ttu-id="0b6a7-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-121">TABLE_TYPE</span></span>|<span data-ttu-id="0b6a7-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-122">String</span></span>|  
|<span data-ttu-id="0b6a7-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-123">TABLE_GUID</span></span>|<span data-ttu-id="0b6a7-124">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-124">Guid</span></span>|  
|<span data-ttu-id="0b6a7-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-125">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-126">String</span></span>|  
|<span data-ttu-id="0b6a7-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-127">TABLE_PROPID</span></span>|<span data-ttu-id="0b6a7-128">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-128">Int64</span></span>|  
|<span data-ttu-id="0b6a7-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-129">DATE_CREATED</span></span>|<span data-ttu-id="0b6a7-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-130">DateTime</span></span>|  
|<span data-ttu-id="0b6a7-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-131">DATE_MODIFIED</span></span>|<span data-ttu-id="0b6a7-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0b6a7-133">Columns</span><span class="sxs-lookup"><span data-stu-id="0b6a7-133">Columns</span></span>  
  
|<span data-ttu-id="0b6a7-134">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-134">ColumnName</span></span>|<span data-ttu-id="0b6a7-135">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-136">TABLE_CATALOG</span></span>|<span data-ttu-id="0b6a7-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-137">String</span></span>|  
|<span data-ttu-id="0b6a7-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-139">String</span></span>|  
|<span data-ttu-id="0b6a7-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-140">TABLE_NAME</span></span>|<span data-ttu-id="0b6a7-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-141">String</span></span>|  
|<span data-ttu-id="0b6a7-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-142">COLUMN_NAME</span></span>|<span data-ttu-id="0b6a7-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-143">String</span></span>|  
|<span data-ttu-id="0b6a7-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-144">COLUMN_GUID</span></span>|<span data-ttu-id="0b6a7-145">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-145">Guid</span></span>|  
|<span data-ttu-id="0b6a7-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-146">COLUMN_PROPID</span></span>|<span data-ttu-id="0b6a7-147">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-147">Int64</span></span>|  
|<span data-ttu-id="0b6a7-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b6a7-149">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-149">Int64</span></span>|  
|<span data-ttu-id="0b6a7-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0b6a7-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="0b6a7-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-151">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0b6a7-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="0b6a7-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-153">String</span></span>|  
|<span data-ttu-id="0b6a7-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0b6a7-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="0b6a7-155">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-155">Int64</span></span>|  
|<span data-ttu-id="0b6a7-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-156">IS_NULLABLE</span></span>|<span data-ttu-id="0b6a7-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-157">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-158">DATA_TYPE</span></span>|<span data-ttu-id="0b6a7-159">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-159">Int32</span></span>|  
|<span data-ttu-id="0b6a7-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-160">TYPE_GUID</span></span>|<span data-ttu-id="0b6a7-161">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-161">Guid</span></span>|  
|<span data-ttu-id="0b6a7-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b6a7-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0b6a7-163">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-163">Int64</span></span>|  
|<span data-ttu-id="0b6a7-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b6a7-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0b6a7-165">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-165">Int64</span></span>|  
|<span data-ttu-id="0b6a7-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0b6a7-167">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-167">Int32</span></span>|  
|<span data-ttu-id="0b6a7-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="0b6a7-169">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-169">Int16</span></span>|  
|<span data-ttu-id="0b6a7-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="0b6a7-171">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-171">Int64</span></span>|  
|<span data-ttu-id="0b6a7-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="0b6a7-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-173">String</span></span>|  
|<span data-ttu-id="0b6a7-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="0b6a7-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-175">String</span></span>|  
|<span data-ttu-id="0b6a7-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="0b6a7-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-177">String</span></span>|  
|<span data-ttu-id="0b6a7-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="0b6a7-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-179">String</span></span>|  
|<span data-ttu-id="0b6a7-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="0b6a7-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-181">String</span></span>|  
|<span data-ttu-id="0b6a7-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-182">COLLATION_NAME</span></span>|<span data-ttu-id="0b6a7-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-183">String</span></span>|  
|<span data-ttu-id="0b6a7-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="0b6a7-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-185">String</span></span>|  
|<span data-ttu-id="0b6a7-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="0b6a7-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-187">String</span></span>|  
|<span data-ttu-id="0b6a7-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-188">DOMAIN_NAME</span></span>|<span data-ttu-id="0b6a7-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-189">String</span></span>|  
|<span data-ttu-id="0b6a7-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-190">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-191">String</span></span>|  
|<span data-ttu-id="0b6a7-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-192">COLUMN_LCID</span></span>|<span data-ttu-id="0b6a7-193">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-193">Int32</span></span>|  
|<span data-ttu-id="0b6a7-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="0b6a7-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="0b6a7-195">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-195">Int32</span></span>|  
|<span data-ttu-id="0b6a7-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-196">COLUMN_SORTID</span></span>|<span data-ttu-id="0b6a7-197">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-197">Int32</span></span>|  
|<span data-ttu-id="0b6a7-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="0b6a7-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="0b6a7-199">Byte[]</span></span>|  
|<span data-ttu-id="0b6a7-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-200">IS_COMPUTED</span></span>|<span data-ttu-id="0b6a7-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0b6a7-202">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b6a7-202">Procedures</span></span>  
  
|<span data-ttu-id="0b6a7-203">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-203">ColumnName</span></span>|<span data-ttu-id="0b6a7-204">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0b6a7-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-206">String</span></span>|  
|<span data-ttu-id="0b6a7-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-208">String</span></span>|  
|<span data-ttu-id="0b6a7-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b6a7-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-210">String</span></span>|  
|<span data-ttu-id="0b6a7-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0b6a7-212">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-212">Int16</span></span>|  
|<span data-ttu-id="0b6a7-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="0b6a7-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-214">String</span></span>|  
|<span data-ttu-id="0b6a7-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-215">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-216">String</span></span>|  
|<span data-ttu-id="0b6a7-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-217">DATE_CREATED</span></span>|<span data-ttu-id="0b6a7-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-218">DateTime</span></span>|  
|<span data-ttu-id="0b6a7-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-219">DATE_MODIFIED</span></span>|<span data-ttu-id="0b6a7-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="0b6a7-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0b6a7-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="0b6a7-222">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-222">ColumnName</span></span>|<span data-ttu-id="0b6a7-223">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0b6a7-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-225">String</span></span>|  
|<span data-ttu-id="0b6a7-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-227">String</span></span>|  
|<span data-ttu-id="0b6a7-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b6a7-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-229">String</span></span>|  
|<span data-ttu-id="0b6a7-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-230">PARAMETER_NAME</span></span>|<span data-ttu-id="0b6a7-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-231">String</span></span>|  
|<span data-ttu-id="0b6a7-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b6a7-233">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-233">Int32</span></span>|  
|<span data-ttu-id="0b6a7-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="0b6a7-235">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-235">Int32</span></span>|  
|<span data-ttu-id="0b6a7-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0b6a7-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="0b6a7-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-237">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0b6a7-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="0b6a7-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-239">String</span></span>|  
|<span data-ttu-id="0b6a7-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-240">IS_NULLABLE</span></span>|<span data-ttu-id="0b6a7-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-241">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-242">DATA_TYPE</span></span>|<span data-ttu-id="0b6a7-243">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-243">Int32</span></span>|  
|<span data-ttu-id="0b6a7-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b6a7-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0b6a7-245">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-245">Int64</span></span>|  
|<span data-ttu-id="0b6a7-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b6a7-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0b6a7-247">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-247">Int64</span></span>|  
|<span data-ttu-id="0b6a7-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0b6a7-249">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-249">Int32</span></span>|  
|<span data-ttu-id="0b6a7-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="0b6a7-251">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-251">Int16</span></span>|  
|<span data-ttu-id="0b6a7-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-252">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-253">String</span></span>|  
|<span data-ttu-id="0b6a7-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-254">TYPE_NAME</span></span>|<span data-ttu-id="0b6a7-255">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-255">String</span></span>|  
|<span data-ttu-id="0b6a7-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="0b6a7-257">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="0b6a7-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="0b6a7-258">Catalog</span></span>  
  
|<span data-ttu-id="0b6a7-259">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-259">ColumnName</span></span>|<span data-ttu-id="0b6a7-260">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-261">CATALOG_NAME</span></span>|<span data-ttu-id="0b6a7-262">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-262">String</span></span>|  
|<span data-ttu-id="0b6a7-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-263">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-264">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0b6a7-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="0b6a7-265">Indexes</span></span>  
  
|<span data-ttu-id="0b6a7-266">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-266">ColumnName</span></span>|<span data-ttu-id="0b6a7-267">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-268">TABLE_CATALOG</span></span>|<span data-ttu-id="0b6a7-269">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-269">String</span></span>|  
|<span data-ttu-id="0b6a7-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-271">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-271">String</span></span>|  
|<span data-ttu-id="0b6a7-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-272">TABLE_NAME</span></span>|<span data-ttu-id="0b6a7-273">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-273">String</span></span>|  
|<span data-ttu-id="0b6a7-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-274">INDEX_CATALOG</span></span>|<span data-ttu-id="0b6a7-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-275">String</span></span>|  
|<span data-ttu-id="0b6a7-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="0b6a7-277">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-277">String</span></span>|  
|<span data-ttu-id="0b6a7-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-278">INDEX_NAME</span></span>|<span data-ttu-id="0b6a7-279">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-279">String</span></span>|  
|<span data-ttu-id="0b6a7-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="0b6a7-280">PRIMARY_KEY</span></span>|<span data-ttu-id="0b6a7-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-281">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-282">UNIQUE</span></span>|<span data-ttu-id="0b6a7-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-283">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-284">CLUSTERED</span></span>|<span data-ttu-id="0b6a7-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-285">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-286">TYPE</span></span>|<span data-ttu-id="0b6a7-287">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-287">Int32</span></span>|  
|<span data-ttu-id="0b6a7-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="0b6a7-288">FILL_FACTOR</span></span>|<span data-ttu-id="0b6a7-289">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-289">Int32</span></span>|  
|<span data-ttu-id="0b6a7-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-290">INITIAL_SIZE</span></span>|<span data-ttu-id="0b6a7-291">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-291">Int32</span></span>|  
|<span data-ttu-id="0b6a7-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="0b6a7-292">NULLS</span></span>|<span data-ttu-id="0b6a7-293">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-293">Int32</span></span>|  
|<span data-ttu-id="0b6a7-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="0b6a7-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="0b6a7-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-295">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-296">AUTO_UPDATE</span></span>|<span data-ttu-id="0b6a7-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-297">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-298">NULL_COLLATION</span></span>|<span data-ttu-id="0b6a7-299">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-299">Int32</span></span>|  
|<span data-ttu-id="0b6a7-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b6a7-301">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-301">Int64</span></span>|  
|<span data-ttu-id="0b6a7-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-302">COLUMN_NAME</span></span>|<span data-ttu-id="0b6a7-303">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-303">String</span></span>|  
|<span data-ttu-id="0b6a7-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-304">COLUMN_GUID</span></span>|<span data-ttu-id="0b6a7-305">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-305">Guid</span></span>|  
|<span data-ttu-id="0b6a7-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-306">COLUMN_PROPID</span></span>|<span data-ttu-id="0b6a7-307">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-307">Int64</span></span>|  
|<span data-ttu-id="0b6a7-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-308">COLLATION</span></span>|<span data-ttu-id="0b6a7-309">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-309">Int16</span></span>|  
|<span data-ttu-id="0b6a7-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="0b6a7-310">CARDINALITY</span></span>|<span data-ttu-id="0b6a7-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="0b6a7-311">Decimal</span></span>|  
|<span data-ttu-id="0b6a7-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="0b6a7-312">PAGES</span></span>|<span data-ttu-id="0b6a7-313">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-313">Int32</span></span>|  
|<span data-ttu-id="0b6a7-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-314">FILTER_CONDITION</span></span>|<span data-ttu-id="0b6a7-315">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-315">String</span></span>|  
|<span data-ttu-id="0b6a7-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-316">INTEGRATED</span></span>|<span data-ttu-id="0b6a7-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="0b6a7-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="0b6a7-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="0b6a7-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="0b6a7-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="0b6a7-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0b6a7-320">Tables</span></span>  
  
-   <span data-ttu-id="0b6a7-321">Columns</span><span class="sxs-lookup"><span data-stu-id="0b6a7-321">Columns</span></span>  
  
-   <span data-ttu-id="0b6a7-322">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b6a7-322">Procedures</span></span>  
  
-   <span data-ttu-id="0b6a7-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0b6a7-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="0b6a7-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0b6a7-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="0b6a7-325">Ansichten</span><span class="sxs-lookup"><span data-stu-id="0b6a7-325">Views</span></span>  
  
-   <span data-ttu-id="0b6a7-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="0b6a7-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="0b6a7-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0b6a7-327">Tables</span></span>  
  
|<span data-ttu-id="0b6a7-328">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-328">ColumnName</span></span>|<span data-ttu-id="0b6a7-329">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-330">TABLE_CATALOG</span></span>|<span data-ttu-id="0b6a7-331">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-331">String</span></span>|  
|<span data-ttu-id="0b6a7-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-333">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-333">String</span></span>|  
|<span data-ttu-id="0b6a7-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-334">TABLE_NAME</span></span>|<span data-ttu-id="0b6a7-335">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-335">String</span></span>|  
|<span data-ttu-id="0b6a7-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-336">TABLE_TYPE</span></span>|<span data-ttu-id="0b6a7-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-337">String</span></span>|  
|<span data-ttu-id="0b6a7-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-338">TABLE_GUID</span></span>|<span data-ttu-id="0b6a7-339">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-339">Guid</span></span>|  
|<span data-ttu-id="0b6a7-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-340">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-341">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-341">String</span></span>|  
|<span data-ttu-id="0b6a7-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-342">TABLE_PROPID</span></span>|<span data-ttu-id="0b6a7-343">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-343">Int64</span></span>|  
|<span data-ttu-id="0b6a7-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-344">DATE_CREATED</span></span>|<span data-ttu-id="0b6a7-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-345">DateTime</span></span>|  
|<span data-ttu-id="0b6a7-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-346">DATE_MODIFIED</span></span>|<span data-ttu-id="0b6a7-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0b6a7-348">Columns</span><span class="sxs-lookup"><span data-stu-id="0b6a7-348">Columns</span></span>  
  
|<span data-ttu-id="0b6a7-349">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-349">ColumnName</span></span>|<span data-ttu-id="0b6a7-350">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-351">TABLE_CATALOG</span></span>|<span data-ttu-id="0b6a7-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-352">String</span></span>|  
|<span data-ttu-id="0b6a7-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-354">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-354">String</span></span>|  
|<span data-ttu-id="0b6a7-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-355">TABLE_NAME</span></span>|<span data-ttu-id="0b6a7-356">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-356">String</span></span>|  
|<span data-ttu-id="0b6a7-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-357">COLUMN_NAME</span></span>|<span data-ttu-id="0b6a7-358">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-358">String</span></span>|  
|<span data-ttu-id="0b6a7-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-359">COLUMN_GUID</span></span>|<span data-ttu-id="0b6a7-360">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-360">Guid</span></span>|  
|<span data-ttu-id="0b6a7-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-361">COLUMN_PROPID</span></span>|<span data-ttu-id="0b6a7-362">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-362">Int64</span></span>|  
|<span data-ttu-id="0b6a7-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b6a7-364">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-364">Int64</span></span>|  
|<span data-ttu-id="0b6a7-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0b6a7-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="0b6a7-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-366">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0b6a7-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="0b6a7-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-368">String</span></span>|  
|<span data-ttu-id="0b6a7-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0b6a7-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="0b6a7-370">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-370">Int64</span></span>|  
|<span data-ttu-id="0b6a7-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-371">IS_NULLABLE</span></span>|<span data-ttu-id="0b6a7-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-372">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-373">DATA_TYPE</span></span>|<span data-ttu-id="0b6a7-374">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-374">Int32</span></span>|  
|<span data-ttu-id="0b6a7-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-375">TYPE_GUID</span></span>|<span data-ttu-id="0b6a7-376">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-376">Guid</span></span>|  
|<span data-ttu-id="0b6a7-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b6a7-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0b6a7-378">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-378">Int64</span></span>|  
|<span data-ttu-id="0b6a7-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b6a7-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0b6a7-380">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-380">Int64</span></span>|  
|<span data-ttu-id="0b6a7-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0b6a7-382">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-382">Int32</span></span>|  
|<span data-ttu-id="0b6a7-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="0b6a7-384">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-384">Int16</span></span>|  
|<span data-ttu-id="0b6a7-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="0b6a7-386">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-386">Int64</span></span>|  
|<span data-ttu-id="0b6a7-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="0b6a7-388">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-388">String</span></span>|  
|<span data-ttu-id="0b6a7-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="0b6a7-390">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-390">String</span></span>|  
|<span data-ttu-id="0b6a7-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="0b6a7-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-392">String</span></span>|  
|<span data-ttu-id="0b6a7-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="0b6a7-394">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-394">String</span></span>|  
|<span data-ttu-id="0b6a7-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="0b6a7-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-396">String</span></span>|  
|<span data-ttu-id="0b6a7-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-397">COLLATION_NAME</span></span>|<span data-ttu-id="0b6a7-398">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-398">String</span></span>|  
|<span data-ttu-id="0b6a7-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="0b6a7-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-400">String</span></span>|  
|<span data-ttu-id="0b6a7-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="0b6a7-402">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-402">String</span></span>|  
|<span data-ttu-id="0b6a7-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-403">DOMAIN_NAME</span></span>|<span data-ttu-id="0b6a7-404">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-404">String</span></span>|  
|<span data-ttu-id="0b6a7-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-405">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-406">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0b6a7-407">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b6a7-407">Procedures</span></span>  
  
|<span data-ttu-id="0b6a7-408">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-408">ColumnName</span></span>|<span data-ttu-id="0b6a7-409">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0b6a7-411">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-411">String</span></span>|  
|<span data-ttu-id="0b6a7-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-413">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-413">String</span></span>|  
|<span data-ttu-id="0b6a7-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b6a7-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-415">String</span></span>|  
|<span data-ttu-id="0b6a7-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0b6a7-417">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-417">Int16</span></span>|  
|<span data-ttu-id="0b6a7-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="0b6a7-419">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-419">String</span></span>|  
|<span data-ttu-id="0b6a7-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-420">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-421">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-421">String</span></span>|  
|<span data-ttu-id="0b6a7-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-422">DATE_CREATED</span></span>|<span data-ttu-id="0b6a7-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-423">DateTime</span></span>|  
|<span data-ttu-id="0b6a7-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-424">DATE_MODIFIED</span></span>|<span data-ttu-id="0b6a7-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="0b6a7-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0b6a7-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="0b6a7-427">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-427">ColumnName</span></span>|<span data-ttu-id="0b6a7-428">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0b6a7-430">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-430">String</span></span>|  
|<span data-ttu-id="0b6a7-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-432">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-432">String</span></span>|  
|<span data-ttu-id="0b6a7-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b6a7-434">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-434">String</span></span>|  
|<span data-ttu-id="0b6a7-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-435">COLUMN_NAME</span></span>|<span data-ttu-id="0b6a7-436">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-436">String</span></span>|  
|<span data-ttu-id="0b6a7-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-437">COLUMN_GUID</span></span>|<span data-ttu-id="0b6a7-438">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-438">Guid</span></span>|  
|<span data-ttu-id="0b6a7-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-439">COLUMN_PROPID</span></span>|<span data-ttu-id="0b6a7-440">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-440">Int64</span></span>|  
|<span data-ttu-id="0b6a7-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="0b6a7-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="0b6a7-442">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-442">Int64</span></span>|  
|<span data-ttu-id="0b6a7-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b6a7-444">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-444">Int64</span></span>|  
|<span data-ttu-id="0b6a7-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-445">IS_NULLABLE</span></span>|<span data-ttu-id="0b6a7-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-446">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-447">DATA_TYPE</span></span>|<span data-ttu-id="0b6a7-448">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-448">Int32</span></span>|  
|<span data-ttu-id="0b6a7-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-449">TYPE_GUID</span></span>|<span data-ttu-id="0b6a7-450">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-450">Guid</span></span>|  
|<span data-ttu-id="0b6a7-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b6a7-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0b6a7-452">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-452">Int64</span></span>|  
|<span data-ttu-id="0b6a7-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b6a7-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0b6a7-454">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-454">Int64</span></span>|  
|<span data-ttu-id="0b6a7-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0b6a7-456">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-456">Int32</span></span>|  
|<span data-ttu-id="0b6a7-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="0b6a7-458">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-458">Int16</span></span>|  
|<span data-ttu-id="0b6a7-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-459">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-460">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-460">String</span></span>|  
|<span data-ttu-id="0b6a7-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="0b6a7-461">OVERLOAD</span></span>|<span data-ttu-id="0b6a7-462">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="0b6a7-463">Ansichten</span><span class="sxs-lookup"><span data-stu-id="0b6a7-463">Views</span></span>  
  
|<span data-ttu-id="0b6a7-464">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-464">ColumnName</span></span>|<span data-ttu-id="0b6a7-465">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-466">TABLE_CATALOG</span></span>|<span data-ttu-id="0b6a7-467">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-467">String</span></span>|  
|<span data-ttu-id="0b6a7-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-469">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-469">String</span></span>|  
|<span data-ttu-id="0b6a7-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-470">TABLE_NAME</span></span>|<span data-ttu-id="0b6a7-471">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-471">String</span></span>|  
|<span data-ttu-id="0b6a7-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="0b6a7-473">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-473">String</span></span>|  
|<span data-ttu-id="0b6a7-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-474">CHECK_OPTION</span></span>|<span data-ttu-id="0b6a7-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-475">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-476">IS_UPDATABLE</span></span>|<span data-ttu-id="0b6a7-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-477">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-478">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-479">String</span></span>|  
|<span data-ttu-id="0b6a7-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-480">DATE_CREATED</span></span>|<span data-ttu-id="0b6a7-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-481">DateTime</span></span>|  
|<span data-ttu-id="0b6a7-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-482">DATE_MODIFIED</span></span>|<span data-ttu-id="0b6a7-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0b6a7-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="0b6a7-484">Indexes</span></span>  
  
|<span data-ttu-id="0b6a7-485">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-485">ColumnName</span></span>|<span data-ttu-id="0b6a7-486">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-487">TABLE_CATALOG</span></span>|<span data-ttu-id="0b6a7-488">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-488">String</span></span>|  
|<span data-ttu-id="0b6a7-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-490">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-490">String</span></span>|  
|<span data-ttu-id="0b6a7-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-491">TABLE_NAME</span></span>|<span data-ttu-id="0b6a7-492">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-492">String</span></span>|  
|<span data-ttu-id="0b6a7-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-493">INDEX_CATALOG</span></span>|<span data-ttu-id="0b6a7-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-494">String</span></span>|  
|<span data-ttu-id="0b6a7-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="0b6a7-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-496">String</span></span>|  
|<span data-ttu-id="0b6a7-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-497">INDEX_NAME</span></span>|<span data-ttu-id="0b6a7-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-498">String</span></span>|  
|<span data-ttu-id="0b6a7-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="0b6a7-499">PRIMARY_KEY</span></span>|<span data-ttu-id="0b6a7-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-500">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-501">UNIQUE</span></span>|<span data-ttu-id="0b6a7-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-502">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-503">CLUSTERED</span></span>|<span data-ttu-id="0b6a7-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-504">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-505">TYPE</span></span>|<span data-ttu-id="0b6a7-506">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-506">Int32</span></span>|  
|<span data-ttu-id="0b6a7-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="0b6a7-507">FILL_FACTOR</span></span>|<span data-ttu-id="0b6a7-508">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-508">Int32</span></span>|  
|<span data-ttu-id="0b6a7-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-509">INITIAL_SIZE</span></span>|<span data-ttu-id="0b6a7-510">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-510">Int32</span></span>|  
|<span data-ttu-id="0b6a7-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="0b6a7-511">NULLS</span></span>|<span data-ttu-id="0b6a7-512">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-512">Int32</span></span>|  
|<span data-ttu-id="0b6a7-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="0b6a7-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="0b6a7-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-514">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-515">AUTO_UPDATE</span></span>|<span data-ttu-id="0b6a7-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-516">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-517">NULL_COLLATION</span></span>|<span data-ttu-id="0b6a7-518">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-518">Int32</span></span>|  
|<span data-ttu-id="0b6a7-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b6a7-520">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-520">Int64</span></span>|  
|<span data-ttu-id="0b6a7-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-521">COLUMN_NAME</span></span>|<span data-ttu-id="0b6a7-522">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-522">String</span></span>|  
|<span data-ttu-id="0b6a7-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-523">COLUMN_GUID</span></span>|<span data-ttu-id="0b6a7-524">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-524">Guid</span></span>|  
|<span data-ttu-id="0b6a7-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-525">COLUMN_PROPID</span></span>|<span data-ttu-id="0b6a7-526">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-526">Int64</span></span>|  
|<span data-ttu-id="0b6a7-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-527">COLLATION</span></span>|<span data-ttu-id="0b6a7-528">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-528">Int16</span></span>|  
|<span data-ttu-id="0b6a7-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="0b6a7-529">CARDINALITY</span></span>|<span data-ttu-id="0b6a7-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="0b6a7-530">Decimal</span></span>|  
|<span data-ttu-id="0b6a7-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="0b6a7-531">PAGES</span></span>|<span data-ttu-id="0b6a7-532">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-532">Int32</span></span>|  
|<span data-ttu-id="0b6a7-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-533">FILTER_CONDITION</span></span>|<span data-ttu-id="0b6a7-534">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-534">String</span></span>|  
|<span data-ttu-id="0b6a7-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-535">INTEGRATED</span></span>|<span data-ttu-id="0b6a7-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="0b6a7-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="0b6a7-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="0b6a7-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="0b6a7-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="0b6a7-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0b6a7-539">Tables</span></span>  
  
-   <span data-ttu-id="0b6a7-540">Columns</span><span class="sxs-lookup"><span data-stu-id="0b6a7-540">Columns</span></span>  
  
-   <span data-ttu-id="0b6a7-541">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b6a7-541">Procedures</span></span>  
  
-   <span data-ttu-id="0b6a7-542">Ansichten</span><span class="sxs-lookup"><span data-stu-id="0b6a7-542">Views</span></span>  
  
-   <span data-ttu-id="0b6a7-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="0b6a7-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="0b6a7-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0b6a7-544">Tables</span></span>  
  
|<span data-ttu-id="0b6a7-545">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-545">ColumnName</span></span>|<span data-ttu-id="0b6a7-546">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-547">TABLE_CATALOG</span></span>|<span data-ttu-id="0b6a7-548">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-548">String</span></span>|  
|<span data-ttu-id="0b6a7-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-550">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-550">String</span></span>|  
|<span data-ttu-id="0b6a7-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-551">TABLE_NAME</span></span>|<span data-ttu-id="0b6a7-552">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-552">String</span></span>|  
|<span data-ttu-id="0b6a7-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-553">TABLE_TYPE</span></span>|<span data-ttu-id="0b6a7-554">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-554">String</span></span>|  
|<span data-ttu-id="0b6a7-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-555">TABLE_GUID</span></span>|<span data-ttu-id="0b6a7-556">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-556">Guid</span></span>|  
|<span data-ttu-id="0b6a7-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-557">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-558">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-558">String</span></span>|  
|<span data-ttu-id="0b6a7-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-559">TABLE_PROPID</span></span>|<span data-ttu-id="0b6a7-560">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-560">Int64</span></span>|  
|<span data-ttu-id="0b6a7-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-561">DATE_CREATED</span></span>|<span data-ttu-id="0b6a7-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-562">DateTime</span></span>|  
|<span data-ttu-id="0b6a7-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-563">DATE_MODIFIED</span></span>|<span data-ttu-id="0b6a7-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0b6a7-565">Columns</span><span class="sxs-lookup"><span data-stu-id="0b6a7-565">Columns</span></span>  
  
|<span data-ttu-id="0b6a7-566">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-566">ColumnName</span></span>|<span data-ttu-id="0b6a7-567">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-568">TABLE_CATALOG</span></span>|<span data-ttu-id="0b6a7-569">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-569">String</span></span>|  
|<span data-ttu-id="0b6a7-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-571">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-571">String</span></span>|  
|<span data-ttu-id="0b6a7-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-572">TABLE_NAME</span></span>|<span data-ttu-id="0b6a7-573">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-573">String</span></span>|  
|<span data-ttu-id="0b6a7-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-574">COLUMN_NAME</span></span>|<span data-ttu-id="0b6a7-575">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-575">String</span></span>|  
|<span data-ttu-id="0b6a7-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-576">COLUMN_GUID</span></span>|<span data-ttu-id="0b6a7-577">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-577">Guid</span></span>|  
|<span data-ttu-id="0b6a7-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-578">COLUMN_PROPID</span></span>|<span data-ttu-id="0b6a7-579">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-579">Int64</span></span>|  
|<span data-ttu-id="0b6a7-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b6a7-581">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-581">Int64</span></span>|  
|<span data-ttu-id="0b6a7-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0b6a7-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="0b6a7-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-583">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0b6a7-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="0b6a7-585">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-585">String</span></span>|  
|<span data-ttu-id="0b6a7-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0b6a7-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="0b6a7-587">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-587">Int64</span></span>|  
|<span data-ttu-id="0b6a7-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-588">IS_NULLABLE</span></span>|<span data-ttu-id="0b6a7-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-589">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-590">DATA_TYPE</span></span>|<span data-ttu-id="0b6a7-591">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-591">Int32</span></span>|  
|<span data-ttu-id="0b6a7-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-592">TYPE_GUID</span></span>|<span data-ttu-id="0b6a7-593">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-593">Guid</span></span>|  
|<span data-ttu-id="0b6a7-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b6a7-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0b6a7-595">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-595">Int64</span></span>|  
|<span data-ttu-id="0b6a7-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b6a7-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0b6a7-597">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-597">Int64</span></span>|  
|<span data-ttu-id="0b6a7-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0b6a7-599">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-599">Int32</span></span>|  
|<span data-ttu-id="0b6a7-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="0b6a7-601">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-601">Int16</span></span>|  
|<span data-ttu-id="0b6a7-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="0b6a7-603">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-603">Int64</span></span>|  
|<span data-ttu-id="0b6a7-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="0b6a7-605">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-605">String</span></span>|  
|<span data-ttu-id="0b6a7-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="0b6a7-607">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-607">String</span></span>|  
|<span data-ttu-id="0b6a7-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="0b6a7-609">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-609">String</span></span>|  
|<span data-ttu-id="0b6a7-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="0b6a7-611">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-611">String</span></span>|  
|<span data-ttu-id="0b6a7-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="0b6a7-613">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-613">String</span></span>|  
|<span data-ttu-id="0b6a7-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-614">COLLATION_NAME</span></span>|<span data-ttu-id="0b6a7-615">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-615">String</span></span>|  
|<span data-ttu-id="0b6a7-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="0b6a7-617">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-617">String</span></span>|  
|<span data-ttu-id="0b6a7-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="0b6a7-619">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-619">String</span></span>|  
|<span data-ttu-id="0b6a7-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-620">DOMAIN_NAME</span></span>|<span data-ttu-id="0b6a7-621">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-621">String</span></span>|  
|<span data-ttu-id="0b6a7-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-622">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-623">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0b6a7-624">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b6a7-624">Procedures</span></span>  
  
|<span data-ttu-id="0b6a7-625">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-625">ColumnName</span></span>|<span data-ttu-id="0b6a7-626">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0b6a7-628">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-628">String</span></span>|  
|<span data-ttu-id="0b6a7-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-630">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-630">String</span></span>|  
|<span data-ttu-id="0b6a7-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b6a7-632">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-632">String</span></span>|  
|<span data-ttu-id="0b6a7-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0b6a7-634">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-634">Int16</span></span>|  
|<span data-ttu-id="0b6a7-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="0b6a7-636">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-636">String</span></span>|  
|<span data-ttu-id="0b6a7-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-637">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-638">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-638">String</span></span>|  
|<span data-ttu-id="0b6a7-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-639">DATE_CREATED</span></span>|<span data-ttu-id="0b6a7-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-640">DateTime</span></span>|  
|<span data-ttu-id="0b6a7-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-641">DATE_MODIFIED</span></span>|<span data-ttu-id="0b6a7-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="0b6a7-643">Ansichten</span><span class="sxs-lookup"><span data-stu-id="0b6a7-643">Views</span></span>  
  
|<span data-ttu-id="0b6a7-644">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-644">ColumnName</span></span>|<span data-ttu-id="0b6a7-645">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-646">TABLE_CATALOG</span></span>|<span data-ttu-id="0b6a7-647">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-647">String</span></span>|  
|<span data-ttu-id="0b6a7-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-649">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-649">String</span></span>|  
|<span data-ttu-id="0b6a7-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-650">TABLE_NAME</span></span>|<span data-ttu-id="0b6a7-651">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-651">String</span></span>|  
|<span data-ttu-id="0b6a7-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="0b6a7-653">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-653">String</span></span>|  
|<span data-ttu-id="0b6a7-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-654">CHECK_OPTION</span></span>|<span data-ttu-id="0b6a7-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-655">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-656">IS_UPDATABLE</span></span>|<span data-ttu-id="0b6a7-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-657">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-658">DESCRIPTION</span></span>|<span data-ttu-id="0b6a7-659">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-659">String</span></span>|  
|<span data-ttu-id="0b6a7-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-660">DATE_CREATED</span></span>|<span data-ttu-id="0b6a7-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-661">DateTime</span></span>|  
|<span data-ttu-id="0b6a7-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-662">DATE_MODIFIED</span></span>|<span data-ttu-id="0b6a7-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="0b6a7-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0b6a7-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="0b6a7-664">Indexes</span></span>  
  
|<span data-ttu-id="0b6a7-665">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b6a7-665">ColumnName</span></span>|<span data-ttu-id="0b6a7-666">DataType</span><span class="sxs-lookup"><span data-stu-id="0b6a7-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b6a7-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-667">TABLE_CATALOG</span></span>|<span data-ttu-id="0b6a7-668">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-668">String</span></span>|  
|<span data-ttu-id="0b6a7-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="0b6a7-670">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-670">String</span></span>|  
|<span data-ttu-id="0b6a7-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-671">TABLE_NAME</span></span>|<span data-ttu-id="0b6a7-672">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-672">String</span></span>|  
|<span data-ttu-id="0b6a7-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b6a7-673">INDEX_CATALOG</span></span>|<span data-ttu-id="0b6a7-674">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-674">String</span></span>|  
|<span data-ttu-id="0b6a7-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b6a7-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="0b6a7-676">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-676">String</span></span>|  
|<span data-ttu-id="0b6a7-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-677">INDEX_NAME</span></span>|<span data-ttu-id="0b6a7-678">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-678">String</span></span>|  
|<span data-ttu-id="0b6a7-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="0b6a7-679">PRIMARY_KEY</span></span>|<span data-ttu-id="0b6a7-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-680">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-681">UNIQUE</span></span>|<span data-ttu-id="0b6a7-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-682">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-683">CLUSTERED</span></span>|<span data-ttu-id="0b6a7-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-684">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-685">TYPE</span></span>|<span data-ttu-id="0b6a7-686">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-686">Int32</span></span>|  
|<span data-ttu-id="0b6a7-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="0b6a7-687">FILL_FACTOR</span></span>|<span data-ttu-id="0b6a7-688">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-688">Int32</span></span>|  
|<span data-ttu-id="0b6a7-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-689">INITIAL_SIZE</span></span>|<span data-ttu-id="0b6a7-690">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-690">Int32</span></span>|  
|<span data-ttu-id="0b6a7-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="0b6a7-691">NULLS</span></span>|<span data-ttu-id="0b6a7-692">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-692">Int32</span></span>|  
|<span data-ttu-id="0b6a7-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="0b6a7-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="0b6a7-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-694">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="0b6a7-695">AUTO_UPDATE</span></span>|<span data-ttu-id="0b6a7-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="0b6a7-696">Boolean</span></span>|  
|<span data-ttu-id="0b6a7-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-697">NULL_COLLATION</span></span>|<span data-ttu-id="0b6a7-698">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-698">Int32</span></span>|  
|<span data-ttu-id="0b6a7-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b6a7-700">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-700">Int64</span></span>|  
|<span data-ttu-id="0b6a7-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b6a7-701">COLUMN_NAME</span></span>|<span data-ttu-id="0b6a7-702">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-702">String</span></span>|  
|<span data-ttu-id="0b6a7-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-703">COLUMN_GUID</span></span>|<span data-ttu-id="0b6a7-704">Guid</span><span class="sxs-lookup"><span data-stu-id="0b6a7-704">Guid</span></span>|  
|<span data-ttu-id="0b6a7-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0b6a7-705">COLUMN_PROPID</span></span>|<span data-ttu-id="0b6a7-706">Int64</span><span class="sxs-lookup"><span data-stu-id="0b6a7-706">Int64</span></span>|  
|<span data-ttu-id="0b6a7-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-707">COLLATION</span></span>|<span data-ttu-id="0b6a7-708">Int16</span><span class="sxs-lookup"><span data-stu-id="0b6a7-708">Int16</span></span>|  
|<span data-ttu-id="0b6a7-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="0b6a7-709">CARDINALITY</span></span>|<span data-ttu-id="0b6a7-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="0b6a7-710">Decimal</span></span>|  
|<span data-ttu-id="0b6a7-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="0b6a7-711">PAGES</span></span>|<span data-ttu-id="0b6a7-712">Int32</span><span class="sxs-lookup"><span data-stu-id="0b6a7-712">Int32</span></span>|  
|<span data-ttu-id="0b6a7-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="0b6a7-713">FILTER_CONDITION</span></span>|<span data-ttu-id="0b6a7-714">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b6a7-714">String</span></span>|  
|<span data-ttu-id="0b6a7-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="0b6a7-715">INTEGRATED</span></span>|<span data-ttu-id="0b6a7-716">Boolesch</span><span class="sxs-lookup"><span data-stu-id="0b6a7-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b6a7-717">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b6a7-717">See Also</span></span>  
 [<span data-ttu-id="0b6a7-718">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="0b6a7-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
