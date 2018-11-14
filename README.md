# Photometric-Stereo
Photometric stereo is a technique to estimate depth and surface orientation from images of the same view taken from different directions. 
Image intensity (Lambertian case): assume that kLj = 1,
  
  Ij(x,y) = k rho(x,y) Ljcos(thetaj)
        = rho(x, y)(n(x, y).sj ) 
        
        -rho(x, y): albedo
        -n(x, y): unknown surface normal vector

  g(x, y) = rho(x, y)n(x, y)

  Solving for g(x, y) gives,  
      I = Sg(x,y)
      g(x, y) = inv(S) I(x, y)
      
  rho(x, y) = |g(x, y)|  <-- since n is a unit vector
  n(x,y) = g(x, y)/|g(x, y)| = g(x, y)/rho(x, y)
  
  For more than 3 light sources,
  I(N*1) = S(N*3)g(3*1)
  transpose(S)I = transpose(S)Sg
  g = inv(transpose(S)S)transpose(S)I    and albedo and surface normal can be calculated as above
  
  Normals are like the “derivative” of the true depth. So, depths can be calculated from normals by Integration method.
