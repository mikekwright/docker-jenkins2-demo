simpleBuild {
 
    env = [
        FOO : 42,
        BAR : "YASS"
    ]
    
    before_script = "echo before && docker ps"
    script = 'echo after $FOO'
    
    notifications = [
        email : "test@test.com"    
    ]
}

