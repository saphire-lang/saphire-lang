task :build do
	puts "==> Building"
	system("crystal build ./saphirelang.saf")
	system("sudo mv saphirelang /usr/bin")
	system("cd ./projects/ && shards && cd ..")
	puts "=> saphire installed with sucess type 'saphire -h to get help' and 'saphire -n' to create a new file"
end
