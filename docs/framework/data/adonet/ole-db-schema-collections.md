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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9b88308c5dad69ed1ba6f48f525931e94f13ef1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="d769c-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="d769c-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="d769c-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="d769c-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="d769c-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d769c-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="d769c-105">Der Microsoft SQL Server OLE DB-Treiber unterstützt die folgenden spezifischen schemaauflistungen zusätzlich zu den allgemeinen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="d769c-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d769c-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d769c-106">Tables</span></span>  
  
-   <span data-ttu-id="d769c-107">Columns</span><span class="sxs-lookup"><span data-stu-id="d769c-107">Columns</span></span>  
  
-   <span data-ttu-id="d769c-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d769c-108">Procedures</span></span>  
  
-   <span data-ttu-id="d769c-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d769c-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d769c-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="d769c-110">Catalog</span></span>  
  
-   <span data-ttu-id="d769c-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="d769c-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d769c-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d769c-112">Tables</span></span>  
  
|<span data-ttu-id="d769c-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-113">ColumnName</span></span>|<span data-ttu-id="d769c-114">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-115">TABLE_CATALOG</span></span>|<span data-ttu-id="d769c-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-116">String</span></span>|  
|<span data-ttu-id="d769c-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="d769c-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-118">String</span></span>|  
|<span data-ttu-id="d769c-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-119">TABLE_NAME</span></span>|<span data-ttu-id="d769c-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-120">String</span></span>|  
|<span data-ttu-id="d769c-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-121">TABLE_TYPE</span></span>|<span data-ttu-id="d769c-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-122">String</span></span>|  
|<span data-ttu-id="d769c-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-123">TABLE_GUID</span></span>|<span data-ttu-id="d769c-124">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-124">Guid</span></span>|  
|<span data-ttu-id="d769c-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-125">DESCRIPTION</span></span>|<span data-ttu-id="d769c-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-126">String</span></span>|  
|<span data-ttu-id="d769c-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d769c-127">TABLE_PROPID</span></span>|<span data-ttu-id="d769c-128">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-128">Int64</span></span>|  
|<span data-ttu-id="d769c-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d769c-129">DATE_CREATED</span></span>|<span data-ttu-id="d769c-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-130">DateTime</span></span>|  
|<span data-ttu-id="d769c-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d769c-131">DATE_MODIFIED</span></span>|<span data-ttu-id="d769c-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d769c-133">Columns</span><span class="sxs-lookup"><span data-stu-id="d769c-133">Columns</span></span>  
  
|<span data-ttu-id="d769c-134">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-134">ColumnName</span></span>|<span data-ttu-id="d769c-135">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-136">TABLE_CATALOG</span></span>|<span data-ttu-id="d769c-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-137">String</span></span>|  
|<span data-ttu-id="d769c-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="d769c-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-139">String</span></span>|  
|<span data-ttu-id="d769c-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-140">TABLE_NAME</span></span>|<span data-ttu-id="d769c-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-141">String</span></span>|  
|<span data-ttu-id="d769c-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-142">COLUMN_NAME</span></span>|<span data-ttu-id="d769c-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-143">String</span></span>|  
|<span data-ttu-id="d769c-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-144">COLUMN_GUID</span></span>|<span data-ttu-id="d769c-145">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-145">Guid</span></span>|  
|<span data-ttu-id="d769c-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d769c-146">COLUMN_PROPID</span></span>|<span data-ttu-id="d769c-147">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-147">Int64</span></span>|  
|<span data-ttu-id="d769c-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d769c-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="d769c-149">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-149">Int64</span></span>|  
|<span data-ttu-id="d769c-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d769c-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d769c-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-151">Boolean</span></span>|  
|<span data-ttu-id="d769c-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d769c-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d769c-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-153">String</span></span>|  
|<span data-ttu-id="d769c-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d769c-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="d769c-155">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-155">Int64</span></span>|  
|<span data-ttu-id="d769c-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d769c-156">IS_NULLABLE</span></span>|<span data-ttu-id="d769c-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-157">Boolean</span></span>|  
|<span data-ttu-id="d769c-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-158">DATA_TYPE</span></span>|<span data-ttu-id="d769c-159">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-159">Int32</span></span>|  
|<span data-ttu-id="d769c-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-160">TYPE_GUID</span></span>|<span data-ttu-id="d769c-161">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-161">Guid</span></span>|  
|<span data-ttu-id="d769c-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d769c-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d769c-163">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-163">Int64</span></span>|  
|<span data-ttu-id="d769c-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d769c-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d769c-165">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-165">Int64</span></span>|  
|<span data-ttu-id="d769c-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d769c-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d769c-167">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-167">Int32</span></span>|  
|<span data-ttu-id="d769c-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d769c-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="d769c-169">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-169">Int16</span></span>|  
|<span data-ttu-id="d769c-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d769c-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="d769c-171">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-171">Int64</span></span>|  
|<span data-ttu-id="d769c-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d769c-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-173">String</span></span>|  
|<span data-ttu-id="d769c-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d769c-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-175">String</span></span>|  
|<span data-ttu-id="d769c-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d769c-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-177">String</span></span>|  
|<span data-ttu-id="d769c-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="d769c-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-179">String</span></span>|  
|<span data-ttu-id="d769c-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d769c-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-181">String</span></span>|  
|<span data-ttu-id="d769c-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-182">COLLATION_NAME</span></span>|<span data-ttu-id="d769c-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-183">String</span></span>|  
|<span data-ttu-id="d769c-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d769c-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-185">String</span></span>|  
|<span data-ttu-id="d769c-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d769c-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-187">String</span></span>|  
|<span data-ttu-id="d769c-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-188">DOMAIN_NAME</span></span>|<span data-ttu-id="d769c-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-189">String</span></span>|  
|<span data-ttu-id="d769c-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-190">DESCRIPTION</span></span>|<span data-ttu-id="d769c-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-191">String</span></span>|  
|<span data-ttu-id="d769c-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="d769c-192">COLUMN_LCID</span></span>|<span data-ttu-id="d769c-193">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-193">Int32</span></span>|  
|<span data-ttu-id="d769c-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="d769c-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="d769c-195">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-195">Int32</span></span>|  
|<span data-ttu-id="d769c-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="d769c-196">COLUMN_SORTID</span></span>|<span data-ttu-id="d769c-197">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-197">Int32</span></span>|  
|<span data-ttu-id="d769c-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="d769c-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="d769c-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="d769c-199">Byte[]</span></span>|  
|<span data-ttu-id="d769c-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="d769c-200">IS_COMPUTED</span></span>|<span data-ttu-id="d769c-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d769c-202">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d769c-202">Procedures</span></span>  
  
|<span data-ttu-id="d769c-203">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-203">ColumnName</span></span>|<span data-ttu-id="d769c-204">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d769c-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-206">String</span></span>|  
|<span data-ttu-id="d769c-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d769c-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-208">String</span></span>|  
|<span data-ttu-id="d769c-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="d769c-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-210">String</span></span>|  
|<span data-ttu-id="d769c-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d769c-212">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-212">Int16</span></span>|  
|<span data-ttu-id="d769c-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d769c-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d769c-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-214">String</span></span>|  
|<span data-ttu-id="d769c-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-215">DESCRIPTION</span></span>|<span data-ttu-id="d769c-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-216">String</span></span>|  
|<span data-ttu-id="d769c-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d769c-217">DATE_CREATED</span></span>|<span data-ttu-id="d769c-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-218">DateTime</span></span>|  
|<span data-ttu-id="d769c-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d769c-219">DATE_MODIFIED</span></span>|<span data-ttu-id="d769c-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d769c-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d769c-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d769c-222">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-222">ColumnName</span></span>|<span data-ttu-id="d769c-223">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d769c-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-225">String</span></span>|  
|<span data-ttu-id="d769c-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d769c-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-227">String</span></span>|  
|<span data-ttu-id="d769c-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="d769c-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-229">String</span></span>|  
|<span data-ttu-id="d769c-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-230">PARAMETER_NAME</span></span>|<span data-ttu-id="d769c-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-231">String</span></span>|  
|<span data-ttu-id="d769c-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d769c-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="d769c-233">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-233">Int32</span></span>|  
|<span data-ttu-id="d769c-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="d769c-235">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-235">Int32</span></span>|  
|<span data-ttu-id="d769c-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d769c-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="d769c-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-237">Boolean</span></span>|  
|<span data-ttu-id="d769c-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d769c-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="d769c-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-239">String</span></span>|  
|<span data-ttu-id="d769c-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d769c-240">IS_NULLABLE</span></span>|<span data-ttu-id="d769c-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-241">Boolean</span></span>|  
|<span data-ttu-id="d769c-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-242">DATA_TYPE</span></span>|<span data-ttu-id="d769c-243">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-243">Int32</span></span>|  
|<span data-ttu-id="d769c-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d769c-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d769c-245">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-245">Int64</span></span>|  
|<span data-ttu-id="d769c-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d769c-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d769c-247">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-247">Int64</span></span>|  
|<span data-ttu-id="d769c-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d769c-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d769c-249">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-249">Int32</span></span>|  
|<span data-ttu-id="d769c-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d769c-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="d769c-251">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-251">Int16</span></span>|  
|<span data-ttu-id="d769c-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-252">DESCRIPTION</span></span>|<span data-ttu-id="d769c-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-253">String</span></span>|  
|<span data-ttu-id="d769c-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-254">TYPE_NAME</span></span>|<span data-ttu-id="d769c-255">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-255">String</span></span>|  
|<span data-ttu-id="d769c-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="d769c-257">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="d769c-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="d769c-258">Catalog</span></span>  
  
|<span data-ttu-id="d769c-259">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-259">ColumnName</span></span>|<span data-ttu-id="d769c-260">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-261">CATALOG_NAME</span></span>|<span data-ttu-id="d769c-262">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-262">String</span></span>|  
|<span data-ttu-id="d769c-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-263">DESCRIPTION</span></span>|<span data-ttu-id="d769c-264">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d769c-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="d769c-265">Indexes</span></span>  
  
|<span data-ttu-id="d769c-266">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-266">ColumnName</span></span>|<span data-ttu-id="d769c-267">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-268">TABLE_CATALOG</span></span>|<span data-ttu-id="d769c-269">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-269">String</span></span>|  
|<span data-ttu-id="d769c-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="d769c-271">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-271">String</span></span>|  
|<span data-ttu-id="d769c-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-272">TABLE_NAME</span></span>|<span data-ttu-id="d769c-273">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-273">String</span></span>|  
|<span data-ttu-id="d769c-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-274">INDEX_CATALOG</span></span>|<span data-ttu-id="d769c-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-275">String</span></span>|  
|<span data-ttu-id="d769c-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="d769c-277">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-277">String</span></span>|  
|<span data-ttu-id="d769c-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-278">INDEX_NAME</span></span>|<span data-ttu-id="d769c-279">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-279">String</span></span>|  
|<span data-ttu-id="d769c-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d769c-280">PRIMARY_KEY</span></span>|<span data-ttu-id="d769c-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-281">Boolean</span></span>|  
|<span data-ttu-id="d769c-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d769c-282">UNIQUE</span></span>|<span data-ttu-id="d769c-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-283">Boolean</span></span>|  
|<span data-ttu-id="d769c-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d769c-284">CLUSTERED</span></span>|<span data-ttu-id="d769c-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-285">Boolean</span></span>|  
|<span data-ttu-id="d769c-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-286">TYPE</span></span>|<span data-ttu-id="d769c-287">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-287">Int32</span></span>|  
|<span data-ttu-id="d769c-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d769c-288">FILL_FACTOR</span></span>|<span data-ttu-id="d769c-289">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-289">Int32</span></span>|  
|<span data-ttu-id="d769c-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d769c-290">INITIAL_SIZE</span></span>|<span data-ttu-id="d769c-291">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-291">Int32</span></span>|  
|<span data-ttu-id="d769c-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="d769c-292">NULLS</span></span>|<span data-ttu-id="d769c-293">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-293">Int32</span></span>|  
|<span data-ttu-id="d769c-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d769c-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d769c-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-295">Boolean</span></span>|  
|<span data-ttu-id="d769c-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d769c-296">AUTO_UPDATE</span></span>|<span data-ttu-id="d769c-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-297">Boolean</span></span>|  
|<span data-ttu-id="d769c-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d769c-298">NULL_COLLATION</span></span>|<span data-ttu-id="d769c-299">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-299">Int32</span></span>|  
|<span data-ttu-id="d769c-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d769c-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="d769c-301">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-301">Int64</span></span>|  
|<span data-ttu-id="d769c-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-302">COLUMN_NAME</span></span>|<span data-ttu-id="d769c-303">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-303">String</span></span>|  
|<span data-ttu-id="d769c-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-304">COLUMN_GUID</span></span>|<span data-ttu-id="d769c-305">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-305">Guid</span></span>|  
|<span data-ttu-id="d769c-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d769c-306">COLUMN_PROPID</span></span>|<span data-ttu-id="d769c-307">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-307">Int64</span></span>|  
|<span data-ttu-id="d769c-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d769c-308">COLLATION</span></span>|<span data-ttu-id="d769c-309">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-309">Int16</span></span>|  
|<span data-ttu-id="d769c-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d769c-310">CARDINALITY</span></span>|<span data-ttu-id="d769c-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="d769c-311">Decimal</span></span>|  
|<span data-ttu-id="d769c-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="d769c-312">PAGES</span></span>|<span data-ttu-id="d769c-313">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-313">Int32</span></span>|  
|<span data-ttu-id="d769c-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d769c-314">FILTER_CONDITION</span></span>|<span data-ttu-id="d769c-315">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-315">String</span></span>|  
|<span data-ttu-id="d769c-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d769c-316">INTEGRATED</span></span>|<span data-ttu-id="d769c-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="d769c-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d769c-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="d769c-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="d769c-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d769c-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d769c-320">Tables</span></span>  
  
-   <span data-ttu-id="d769c-321">Columns</span><span class="sxs-lookup"><span data-stu-id="d769c-321">Columns</span></span>  
  
-   <span data-ttu-id="d769c-322">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d769c-322">Procedures</span></span>  
  
-   <span data-ttu-id="d769c-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d769c-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="d769c-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d769c-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d769c-325">Ansichten</span><span class="sxs-lookup"><span data-stu-id="d769c-325">Views</span></span>  
  
-   <span data-ttu-id="d769c-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="d769c-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d769c-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d769c-327">Tables</span></span>  
  
|<span data-ttu-id="d769c-328">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-328">ColumnName</span></span>|<span data-ttu-id="d769c-329">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-330">TABLE_CATALOG</span></span>|<span data-ttu-id="d769c-331">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-331">String</span></span>|  
|<span data-ttu-id="d769c-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="d769c-333">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-333">String</span></span>|  
|<span data-ttu-id="d769c-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-334">TABLE_NAME</span></span>|<span data-ttu-id="d769c-335">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-335">String</span></span>|  
|<span data-ttu-id="d769c-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-336">TABLE_TYPE</span></span>|<span data-ttu-id="d769c-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-337">String</span></span>|  
|<span data-ttu-id="d769c-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-338">TABLE_GUID</span></span>|<span data-ttu-id="d769c-339">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-339">Guid</span></span>|  
|<span data-ttu-id="d769c-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-340">DESCRIPTION</span></span>|<span data-ttu-id="d769c-341">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-341">String</span></span>|  
|<span data-ttu-id="d769c-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d769c-342">TABLE_PROPID</span></span>|<span data-ttu-id="d769c-343">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-343">Int64</span></span>|  
|<span data-ttu-id="d769c-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d769c-344">DATE_CREATED</span></span>|<span data-ttu-id="d769c-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-345">DateTime</span></span>|  
|<span data-ttu-id="d769c-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d769c-346">DATE_MODIFIED</span></span>|<span data-ttu-id="d769c-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d769c-348">Columns</span><span class="sxs-lookup"><span data-stu-id="d769c-348">Columns</span></span>  
  
|<span data-ttu-id="d769c-349">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-349">ColumnName</span></span>|<span data-ttu-id="d769c-350">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-351">TABLE_CATALOG</span></span>|<span data-ttu-id="d769c-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-352">String</span></span>|  
|<span data-ttu-id="d769c-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="d769c-354">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-354">String</span></span>|  
|<span data-ttu-id="d769c-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-355">TABLE_NAME</span></span>|<span data-ttu-id="d769c-356">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-356">String</span></span>|  
|<span data-ttu-id="d769c-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-357">COLUMN_NAME</span></span>|<span data-ttu-id="d769c-358">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-358">String</span></span>|  
|<span data-ttu-id="d769c-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-359">COLUMN_GUID</span></span>|<span data-ttu-id="d769c-360">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-360">Guid</span></span>|  
|<span data-ttu-id="d769c-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d769c-361">COLUMN_PROPID</span></span>|<span data-ttu-id="d769c-362">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-362">Int64</span></span>|  
|<span data-ttu-id="d769c-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d769c-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="d769c-364">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-364">Int64</span></span>|  
|<span data-ttu-id="d769c-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d769c-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d769c-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-366">Boolean</span></span>|  
|<span data-ttu-id="d769c-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d769c-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d769c-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-368">String</span></span>|  
|<span data-ttu-id="d769c-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d769c-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="d769c-370">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-370">Int64</span></span>|  
|<span data-ttu-id="d769c-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d769c-371">IS_NULLABLE</span></span>|<span data-ttu-id="d769c-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-372">Boolean</span></span>|  
|<span data-ttu-id="d769c-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-373">DATA_TYPE</span></span>|<span data-ttu-id="d769c-374">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-374">Int32</span></span>|  
|<span data-ttu-id="d769c-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-375">TYPE_GUID</span></span>|<span data-ttu-id="d769c-376">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-376">Guid</span></span>|  
|<span data-ttu-id="d769c-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d769c-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d769c-378">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-378">Int64</span></span>|  
|<span data-ttu-id="d769c-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d769c-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d769c-380">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-380">Int64</span></span>|  
|<span data-ttu-id="d769c-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d769c-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d769c-382">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-382">Int32</span></span>|  
|<span data-ttu-id="d769c-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d769c-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="d769c-384">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-384">Int16</span></span>|  
|<span data-ttu-id="d769c-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d769c-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="d769c-386">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-386">Int64</span></span>|  
|<span data-ttu-id="d769c-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d769c-388">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-388">String</span></span>|  
|<span data-ttu-id="d769c-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d769c-390">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-390">String</span></span>|  
|<span data-ttu-id="d769c-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d769c-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-392">String</span></span>|  
|<span data-ttu-id="d769c-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="d769c-394">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-394">String</span></span>|  
|<span data-ttu-id="d769c-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d769c-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-396">String</span></span>|  
|<span data-ttu-id="d769c-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-397">COLLATION_NAME</span></span>|<span data-ttu-id="d769c-398">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-398">String</span></span>|  
|<span data-ttu-id="d769c-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d769c-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-400">String</span></span>|  
|<span data-ttu-id="d769c-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d769c-402">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-402">String</span></span>|  
|<span data-ttu-id="d769c-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-403">DOMAIN_NAME</span></span>|<span data-ttu-id="d769c-404">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-404">String</span></span>|  
|<span data-ttu-id="d769c-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-405">DESCRIPTION</span></span>|<span data-ttu-id="d769c-406">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d769c-407">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d769c-407">Procedures</span></span>  
  
|<span data-ttu-id="d769c-408">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-408">ColumnName</span></span>|<span data-ttu-id="d769c-409">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d769c-411">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-411">String</span></span>|  
|<span data-ttu-id="d769c-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d769c-413">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-413">String</span></span>|  
|<span data-ttu-id="d769c-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="d769c-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-415">String</span></span>|  
|<span data-ttu-id="d769c-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d769c-417">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-417">Int16</span></span>|  
|<span data-ttu-id="d769c-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d769c-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d769c-419">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-419">String</span></span>|  
|<span data-ttu-id="d769c-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-420">DESCRIPTION</span></span>|<span data-ttu-id="d769c-421">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-421">String</span></span>|  
|<span data-ttu-id="d769c-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d769c-422">DATE_CREATED</span></span>|<span data-ttu-id="d769c-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-423">DateTime</span></span>|  
|<span data-ttu-id="d769c-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d769c-424">DATE_MODIFIED</span></span>|<span data-ttu-id="d769c-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="d769c-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d769c-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="d769c-427">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-427">ColumnName</span></span>|<span data-ttu-id="d769c-428">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d769c-430">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-430">String</span></span>|  
|<span data-ttu-id="d769c-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d769c-432">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-432">String</span></span>|  
|<span data-ttu-id="d769c-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="d769c-434">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-434">String</span></span>|  
|<span data-ttu-id="d769c-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-435">COLUMN_NAME</span></span>|<span data-ttu-id="d769c-436">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-436">String</span></span>|  
|<span data-ttu-id="d769c-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-437">COLUMN_GUID</span></span>|<span data-ttu-id="d769c-438">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-438">Guid</span></span>|  
|<span data-ttu-id="d769c-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d769c-439">COLUMN_PROPID</span></span>|<span data-ttu-id="d769c-440">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-440">Int64</span></span>|  
|<span data-ttu-id="d769c-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="d769c-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="d769c-442">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-442">Int64</span></span>|  
|<span data-ttu-id="d769c-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d769c-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="d769c-444">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-444">Int64</span></span>|  
|<span data-ttu-id="d769c-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d769c-445">IS_NULLABLE</span></span>|<span data-ttu-id="d769c-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-446">Boolean</span></span>|  
|<span data-ttu-id="d769c-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-447">DATA_TYPE</span></span>|<span data-ttu-id="d769c-448">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-448">Int32</span></span>|  
|<span data-ttu-id="d769c-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-449">TYPE_GUID</span></span>|<span data-ttu-id="d769c-450">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-450">Guid</span></span>|  
|<span data-ttu-id="d769c-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d769c-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d769c-452">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-452">Int64</span></span>|  
|<span data-ttu-id="d769c-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d769c-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d769c-454">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-454">Int64</span></span>|  
|<span data-ttu-id="d769c-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d769c-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d769c-456">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-456">Int32</span></span>|  
|<span data-ttu-id="d769c-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d769c-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="d769c-458">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-458">Int16</span></span>|  
|<span data-ttu-id="d769c-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-459">DESCRIPTION</span></span>|<span data-ttu-id="d769c-460">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-460">String</span></span>|  
|<span data-ttu-id="d769c-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d769c-461">OVERLOAD</span></span>|<span data-ttu-id="d769c-462">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d769c-463">Ansichten</span><span class="sxs-lookup"><span data-stu-id="d769c-463">Views</span></span>  
  
|<span data-ttu-id="d769c-464">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-464">ColumnName</span></span>|<span data-ttu-id="d769c-465">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-466">TABLE_CATALOG</span></span>|<span data-ttu-id="d769c-467">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-467">String</span></span>|  
|<span data-ttu-id="d769c-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="d769c-469">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-469">String</span></span>|  
|<span data-ttu-id="d769c-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-470">TABLE_NAME</span></span>|<span data-ttu-id="d769c-471">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-471">String</span></span>|  
|<span data-ttu-id="d769c-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d769c-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="d769c-473">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-473">String</span></span>|  
|<span data-ttu-id="d769c-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-474">CHECK_OPTION</span></span>|<span data-ttu-id="d769c-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-475">Boolean</span></span>|  
|<span data-ttu-id="d769c-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="d769c-476">IS_UPDATABLE</span></span>|<span data-ttu-id="d769c-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-477">Boolean</span></span>|  
|<span data-ttu-id="d769c-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-478">DESCRIPTION</span></span>|<span data-ttu-id="d769c-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-479">String</span></span>|  
|<span data-ttu-id="d769c-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d769c-480">DATE_CREATED</span></span>|<span data-ttu-id="d769c-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-481">DateTime</span></span>|  
|<span data-ttu-id="d769c-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d769c-482">DATE_MODIFIED</span></span>|<span data-ttu-id="d769c-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d769c-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="d769c-484">Indexes</span></span>  
  
|<span data-ttu-id="d769c-485">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-485">ColumnName</span></span>|<span data-ttu-id="d769c-486">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-487">TABLE_CATALOG</span></span>|<span data-ttu-id="d769c-488">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-488">String</span></span>|  
|<span data-ttu-id="d769c-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="d769c-490">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-490">String</span></span>|  
|<span data-ttu-id="d769c-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-491">TABLE_NAME</span></span>|<span data-ttu-id="d769c-492">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-492">String</span></span>|  
|<span data-ttu-id="d769c-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-493">INDEX_CATALOG</span></span>|<span data-ttu-id="d769c-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-494">String</span></span>|  
|<span data-ttu-id="d769c-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="d769c-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-496">String</span></span>|  
|<span data-ttu-id="d769c-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-497">INDEX_NAME</span></span>|<span data-ttu-id="d769c-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-498">String</span></span>|  
|<span data-ttu-id="d769c-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d769c-499">PRIMARY_KEY</span></span>|<span data-ttu-id="d769c-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-500">Boolean</span></span>|  
|<span data-ttu-id="d769c-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d769c-501">UNIQUE</span></span>|<span data-ttu-id="d769c-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-502">Boolean</span></span>|  
|<span data-ttu-id="d769c-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d769c-503">CLUSTERED</span></span>|<span data-ttu-id="d769c-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-504">Boolean</span></span>|  
|<span data-ttu-id="d769c-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-505">TYPE</span></span>|<span data-ttu-id="d769c-506">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-506">Int32</span></span>|  
|<span data-ttu-id="d769c-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d769c-507">FILL_FACTOR</span></span>|<span data-ttu-id="d769c-508">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-508">Int32</span></span>|  
|<span data-ttu-id="d769c-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d769c-509">INITIAL_SIZE</span></span>|<span data-ttu-id="d769c-510">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-510">Int32</span></span>|  
|<span data-ttu-id="d769c-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="d769c-511">NULLS</span></span>|<span data-ttu-id="d769c-512">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-512">Int32</span></span>|  
|<span data-ttu-id="d769c-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d769c-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d769c-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-514">Boolean</span></span>|  
|<span data-ttu-id="d769c-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d769c-515">AUTO_UPDATE</span></span>|<span data-ttu-id="d769c-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-516">Boolean</span></span>|  
|<span data-ttu-id="d769c-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d769c-517">NULL_COLLATION</span></span>|<span data-ttu-id="d769c-518">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-518">Int32</span></span>|  
|<span data-ttu-id="d769c-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d769c-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="d769c-520">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-520">Int64</span></span>|  
|<span data-ttu-id="d769c-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-521">COLUMN_NAME</span></span>|<span data-ttu-id="d769c-522">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-522">String</span></span>|  
|<span data-ttu-id="d769c-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-523">COLUMN_GUID</span></span>|<span data-ttu-id="d769c-524">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-524">Guid</span></span>|  
|<span data-ttu-id="d769c-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d769c-525">COLUMN_PROPID</span></span>|<span data-ttu-id="d769c-526">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-526">Int64</span></span>|  
|<span data-ttu-id="d769c-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d769c-527">COLLATION</span></span>|<span data-ttu-id="d769c-528">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-528">Int16</span></span>|  
|<span data-ttu-id="d769c-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d769c-529">CARDINALITY</span></span>|<span data-ttu-id="d769c-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="d769c-530">Decimal</span></span>|  
|<span data-ttu-id="d769c-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="d769c-531">PAGES</span></span>|<span data-ttu-id="d769c-532">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-532">Int32</span></span>|  
|<span data-ttu-id="d769c-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d769c-533">FILTER_CONDITION</span></span>|<span data-ttu-id="d769c-534">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-534">String</span></span>|  
|<span data-ttu-id="d769c-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d769c-535">INTEGRATED</span></span>|<span data-ttu-id="d769c-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="d769c-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d769c-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="d769c-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="d769c-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d769c-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d769c-539">Tables</span></span>  
  
-   <span data-ttu-id="d769c-540">Columns</span><span class="sxs-lookup"><span data-stu-id="d769c-540">Columns</span></span>  
  
-   <span data-ttu-id="d769c-541">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d769c-541">Procedures</span></span>  
  
-   <span data-ttu-id="d769c-542">Ansichten</span><span class="sxs-lookup"><span data-stu-id="d769c-542">Views</span></span>  
  
-   <span data-ttu-id="d769c-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="d769c-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d769c-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d769c-544">Tables</span></span>  
  
|<span data-ttu-id="d769c-545">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-545">ColumnName</span></span>|<span data-ttu-id="d769c-546">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-547">TABLE_CATALOG</span></span>|<span data-ttu-id="d769c-548">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-548">String</span></span>|  
|<span data-ttu-id="d769c-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="d769c-550">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-550">String</span></span>|  
|<span data-ttu-id="d769c-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-551">TABLE_NAME</span></span>|<span data-ttu-id="d769c-552">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-552">String</span></span>|  
|<span data-ttu-id="d769c-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-553">TABLE_TYPE</span></span>|<span data-ttu-id="d769c-554">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-554">String</span></span>|  
|<span data-ttu-id="d769c-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-555">TABLE_GUID</span></span>|<span data-ttu-id="d769c-556">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-556">Guid</span></span>|  
|<span data-ttu-id="d769c-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-557">DESCRIPTION</span></span>|<span data-ttu-id="d769c-558">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-558">String</span></span>|  
|<span data-ttu-id="d769c-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d769c-559">TABLE_PROPID</span></span>|<span data-ttu-id="d769c-560">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-560">Int64</span></span>|  
|<span data-ttu-id="d769c-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d769c-561">DATE_CREATED</span></span>|<span data-ttu-id="d769c-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-562">DateTime</span></span>|  
|<span data-ttu-id="d769c-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d769c-563">DATE_MODIFIED</span></span>|<span data-ttu-id="d769c-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d769c-565">Columns</span><span class="sxs-lookup"><span data-stu-id="d769c-565">Columns</span></span>  
  
|<span data-ttu-id="d769c-566">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-566">ColumnName</span></span>|<span data-ttu-id="d769c-567">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-568">TABLE_CATALOG</span></span>|<span data-ttu-id="d769c-569">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-569">String</span></span>|  
|<span data-ttu-id="d769c-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="d769c-571">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-571">String</span></span>|  
|<span data-ttu-id="d769c-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-572">TABLE_NAME</span></span>|<span data-ttu-id="d769c-573">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-573">String</span></span>|  
|<span data-ttu-id="d769c-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-574">COLUMN_NAME</span></span>|<span data-ttu-id="d769c-575">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-575">String</span></span>|  
|<span data-ttu-id="d769c-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-576">COLUMN_GUID</span></span>|<span data-ttu-id="d769c-577">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-577">Guid</span></span>|  
|<span data-ttu-id="d769c-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d769c-578">COLUMN_PROPID</span></span>|<span data-ttu-id="d769c-579">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-579">Int64</span></span>|  
|<span data-ttu-id="d769c-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d769c-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="d769c-581">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-581">Int64</span></span>|  
|<span data-ttu-id="d769c-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d769c-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d769c-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-583">Boolean</span></span>|  
|<span data-ttu-id="d769c-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d769c-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d769c-585">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-585">String</span></span>|  
|<span data-ttu-id="d769c-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d769c-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="d769c-587">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-587">Int64</span></span>|  
|<span data-ttu-id="d769c-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d769c-588">IS_NULLABLE</span></span>|<span data-ttu-id="d769c-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-589">Boolean</span></span>|  
|<span data-ttu-id="d769c-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-590">DATA_TYPE</span></span>|<span data-ttu-id="d769c-591">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-591">Int32</span></span>|  
|<span data-ttu-id="d769c-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-592">TYPE_GUID</span></span>|<span data-ttu-id="d769c-593">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-593">Guid</span></span>|  
|<span data-ttu-id="d769c-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d769c-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d769c-595">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-595">Int64</span></span>|  
|<span data-ttu-id="d769c-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d769c-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d769c-597">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-597">Int64</span></span>|  
|<span data-ttu-id="d769c-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d769c-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d769c-599">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-599">Int32</span></span>|  
|<span data-ttu-id="d769c-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d769c-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="d769c-601">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-601">Int16</span></span>|  
|<span data-ttu-id="d769c-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d769c-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="d769c-603">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-603">Int64</span></span>|  
|<span data-ttu-id="d769c-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d769c-605">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-605">String</span></span>|  
|<span data-ttu-id="d769c-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d769c-607">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-607">String</span></span>|  
|<span data-ttu-id="d769c-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d769c-609">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-609">String</span></span>|  
|<span data-ttu-id="d769c-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="d769c-611">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-611">String</span></span>|  
|<span data-ttu-id="d769c-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d769c-613">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-613">String</span></span>|  
|<span data-ttu-id="d769c-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-614">COLLATION_NAME</span></span>|<span data-ttu-id="d769c-615">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-615">String</span></span>|  
|<span data-ttu-id="d769c-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d769c-617">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-617">String</span></span>|  
|<span data-ttu-id="d769c-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d769c-619">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-619">String</span></span>|  
|<span data-ttu-id="d769c-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-620">DOMAIN_NAME</span></span>|<span data-ttu-id="d769c-621">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-621">String</span></span>|  
|<span data-ttu-id="d769c-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-622">DESCRIPTION</span></span>|<span data-ttu-id="d769c-623">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d769c-624">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d769c-624">Procedures</span></span>  
  
|<span data-ttu-id="d769c-625">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-625">ColumnName</span></span>|<span data-ttu-id="d769c-626">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d769c-628">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-628">String</span></span>|  
|<span data-ttu-id="d769c-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d769c-630">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-630">String</span></span>|  
|<span data-ttu-id="d769c-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="d769c-632">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-632">String</span></span>|  
|<span data-ttu-id="d769c-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d769c-634">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-634">Int16</span></span>|  
|<span data-ttu-id="d769c-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d769c-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d769c-636">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-636">String</span></span>|  
|<span data-ttu-id="d769c-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-637">DESCRIPTION</span></span>|<span data-ttu-id="d769c-638">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-638">String</span></span>|  
|<span data-ttu-id="d769c-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d769c-639">DATE_CREATED</span></span>|<span data-ttu-id="d769c-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-640">DateTime</span></span>|  
|<span data-ttu-id="d769c-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d769c-641">DATE_MODIFIED</span></span>|<span data-ttu-id="d769c-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d769c-643">Ansichten</span><span class="sxs-lookup"><span data-stu-id="d769c-643">Views</span></span>  
  
|<span data-ttu-id="d769c-644">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-644">ColumnName</span></span>|<span data-ttu-id="d769c-645">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-646">TABLE_CATALOG</span></span>|<span data-ttu-id="d769c-647">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-647">String</span></span>|  
|<span data-ttu-id="d769c-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="d769c-649">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-649">String</span></span>|  
|<span data-ttu-id="d769c-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-650">TABLE_NAME</span></span>|<span data-ttu-id="d769c-651">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-651">String</span></span>|  
|<span data-ttu-id="d769c-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d769c-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="d769c-653">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-653">String</span></span>|  
|<span data-ttu-id="d769c-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-654">CHECK_OPTION</span></span>|<span data-ttu-id="d769c-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-655">Boolean</span></span>|  
|<span data-ttu-id="d769c-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="d769c-656">IS_UPDATABLE</span></span>|<span data-ttu-id="d769c-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-657">Boolean</span></span>|  
|<span data-ttu-id="d769c-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d769c-658">DESCRIPTION</span></span>|<span data-ttu-id="d769c-659">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-659">String</span></span>|  
|<span data-ttu-id="d769c-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d769c-660">DATE_CREATED</span></span>|<span data-ttu-id="d769c-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-661">DateTime</span></span>|  
|<span data-ttu-id="d769c-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d769c-662">DATE_MODIFIED</span></span>|<span data-ttu-id="d769c-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="d769c-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d769c-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="d769c-664">Indexes</span></span>  
  
|<span data-ttu-id="d769c-665">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d769c-665">ColumnName</span></span>|<span data-ttu-id="d769c-666">DataType</span><span class="sxs-lookup"><span data-stu-id="d769c-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d769c-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-667">TABLE_CATALOG</span></span>|<span data-ttu-id="d769c-668">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-668">String</span></span>|  
|<span data-ttu-id="d769c-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="d769c-670">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-670">String</span></span>|  
|<span data-ttu-id="d769c-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-671">TABLE_NAME</span></span>|<span data-ttu-id="d769c-672">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-672">String</span></span>|  
|<span data-ttu-id="d769c-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d769c-673">INDEX_CATALOG</span></span>|<span data-ttu-id="d769c-674">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-674">String</span></span>|  
|<span data-ttu-id="d769c-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d769c-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="d769c-676">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-676">String</span></span>|  
|<span data-ttu-id="d769c-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-677">INDEX_NAME</span></span>|<span data-ttu-id="d769c-678">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-678">String</span></span>|  
|<span data-ttu-id="d769c-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d769c-679">PRIMARY_KEY</span></span>|<span data-ttu-id="d769c-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-680">Boolean</span></span>|  
|<span data-ttu-id="d769c-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d769c-681">UNIQUE</span></span>|<span data-ttu-id="d769c-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-682">Boolean</span></span>|  
|<span data-ttu-id="d769c-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d769c-683">CLUSTERED</span></span>|<span data-ttu-id="d769c-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-684">Boolean</span></span>|  
|<span data-ttu-id="d769c-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="d769c-685">TYPE</span></span>|<span data-ttu-id="d769c-686">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-686">Int32</span></span>|  
|<span data-ttu-id="d769c-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d769c-687">FILL_FACTOR</span></span>|<span data-ttu-id="d769c-688">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-688">Int32</span></span>|  
|<span data-ttu-id="d769c-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d769c-689">INITIAL_SIZE</span></span>|<span data-ttu-id="d769c-690">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-690">Int32</span></span>|  
|<span data-ttu-id="d769c-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="d769c-691">NULLS</span></span>|<span data-ttu-id="d769c-692">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-692">Int32</span></span>|  
|<span data-ttu-id="d769c-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d769c-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d769c-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-694">Boolean</span></span>|  
|<span data-ttu-id="d769c-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d769c-695">AUTO_UPDATE</span></span>|<span data-ttu-id="d769c-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="d769c-696">Boolean</span></span>|  
|<span data-ttu-id="d769c-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d769c-697">NULL_COLLATION</span></span>|<span data-ttu-id="d769c-698">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-698">Int32</span></span>|  
|<span data-ttu-id="d769c-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d769c-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="d769c-700">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-700">Int64</span></span>|  
|<span data-ttu-id="d769c-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d769c-701">COLUMN_NAME</span></span>|<span data-ttu-id="d769c-702">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-702">String</span></span>|  
|<span data-ttu-id="d769c-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d769c-703">COLUMN_GUID</span></span>|<span data-ttu-id="d769c-704">Guid</span><span class="sxs-lookup"><span data-stu-id="d769c-704">Guid</span></span>|  
|<span data-ttu-id="d769c-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d769c-705">COLUMN_PROPID</span></span>|<span data-ttu-id="d769c-706">Int64</span><span class="sxs-lookup"><span data-stu-id="d769c-706">Int64</span></span>|  
|<span data-ttu-id="d769c-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d769c-707">COLLATION</span></span>|<span data-ttu-id="d769c-708">Int16</span><span class="sxs-lookup"><span data-stu-id="d769c-708">Int16</span></span>|  
|<span data-ttu-id="d769c-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d769c-709">CARDINALITY</span></span>|<span data-ttu-id="d769c-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="d769c-710">Decimal</span></span>|  
|<span data-ttu-id="d769c-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="d769c-711">PAGES</span></span>|<span data-ttu-id="d769c-712">Int32</span><span class="sxs-lookup"><span data-stu-id="d769c-712">Int32</span></span>|  
|<span data-ttu-id="d769c-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d769c-713">FILTER_CONDITION</span></span>|<span data-ttu-id="d769c-714">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d769c-714">String</span></span>|  
|<span data-ttu-id="d769c-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d769c-715">INTEGRATED</span></span>|<span data-ttu-id="d769c-716">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d769c-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d769c-717">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d769c-717">See Also</span></span>  
 [<span data-ttu-id="d769c-718">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="d769c-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
