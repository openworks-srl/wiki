da powershell:
New-CsApplicationAccessPolicy -Identity Test-policy-1 -AppIds "f9f5ed50-4678-4ada-b175-a9dbfc69f48a" -Description "prima policy di test"



Grant-CsApplicationAccessPolicy -PolicyName Test-policy -Global
