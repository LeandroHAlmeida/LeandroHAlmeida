## Script: Criar VMs Azure para A3
## Autor: Leandro Almeida
## Data: Outubro/24

# Definir variáveis
$resourceGroupName = "rg-usjt-a3-systems-compute"
$location01 = "eastus"
$vmm2: "m2"
$vnet: "vnet-usjt-a3"
$subnet:


#Criar VMs m2,m3,m4 e m5

#Váriável

Get-AzVMImageSku -Location "eastus" -PublisherName "Debian" -Offer "debian-12"

New-AzVm `
    -ResourceGroupName "rg-usjt-a3-systems-compute" `
    -Name "m2" `
    -Location 'East US' `
    -image debian-12 `
    -VirtualNetworkName "vnet-usjt-a3" `
    -SubnetName "subnet-a3" `
    -size Standard_B2s `
    -OpenPorts 22 `
    -GenerateSshKey `
    -SshKeyName mySSHKeym2 `

New-AzVm `
    -ResourceGroupName "rg-usjt-a3-systems-compute" `
    -Name "m3" `
    -Location 'East US' `
    -image $image`
    -VirtualNetworkName "vnet-usjt-a3" `
    -SubnetName "subnet-a3" `
    -size Standard_B2s `
    -OpenPorts 22 `
    -GenerateSshKey `
    -SshKeyName mySSHKeym3 `

  New-AzVm `
    -ResourceGroupName "rg-usjt-a3-systems-compute" `
    -Name "m4" `
    -Location 'East US' `
    -image $image `
    -VirtualNetworkName "vnet-usjt-a3" `
    -SubnetName "subnet-a3" `
    -size Standard_B2s `
    -OpenPorts 22 `
    -GenerateSshKey `
    -SshKeyName mySSHKeym4 `

  New-AzVm `
    -ResourceGroupName "rg-usjt-a3-systems-compute" `
    -Name "m5" `
    -Location 'East US' `
    -image $image `
    -VirtualNetworkName "vnet-usjt-a3" `
    -SubnetName "subnet-a3" `
    -size Standard_B2s `
    -OpenPorts 22 `
    -GenerateSshKey `
    -SshKeyName mySSHKeym5 `

Write-Output "VMs foram criadas!"



    
