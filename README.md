1. Subdomains (subfinder)
2. Detect WAF ( My tool)
3. Find Origin IPs ( command )
4. Scan Ports ( nmap ) 
5. Find Urls ( gau and waybackurls )
6. Find Param based urls ( regx )
7. Find  live Urls ( httpx )
8. Run GF pattern
9. Test Specific Vulnability
10. Find .js Urls ( run our tool )
11. Find Directory ( dirsearch & ffuf )
12. Run Nuclei ( if detect then do exploit )
13. Run BLC 
14. Run Zip finder
15. Than Manual Hunting


mkdir -p gf-output  # Create output folder if it doesn't exist

for pattern in ~/.gf/*.json; do
    name=$(basename "$pattern" .json)
    echo -e "\e[1;32m[+] Running pattern: $name\e[0m"
    cat /home/kali/tools/sk.txt | gf "$name" > "gf-output/${name}.txt"
done

